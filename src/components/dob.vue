<template>
  <body>
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&display=swap">
    <div class="main">
      <div class="date1">
        <label
          class="labelname"
          prop="name"
          style=" padding-right:30px; font-size: 23px; color: white;"
          >Enter Birth Date:
        </label>
        <el-date-picker
          v-model="dt"
          type="date"
          placeholder="Pick a day"
          
        ></el-date-picker>
        <div class="outputs-wrapper">
            <div >
                
                <p style="margin-top: 10px;font-size: 30px; color: red;">
                    {{age}}
                </p>
                <p style="padding-top: 20px; font-size: 20px; color: red;"> Years </p>
            </div>
            <div>
                
                <p  style="margin-top: 10px; font-size: 30px; color: green;">
                    {{month}}
                </p>
                <p style="padding-top: 20px; font-size: 20px; color: green;"> Months </p>
            </div>
            <div>
                
                <p  style="margin-top: 10px; font-size: 30px; color: blue;">
                    {{day}}
                </p>
                <p style="padding-top: 20px; font-size: 20px; color: blue;"> Days </p>
            </div>
            
        </div>
      </div>
     
    </div>
  </body>
</template>

<style>

body {
  background: black;
}

.outputs-wrapper{
    width: 100%;
    display: flex;
    justify-content:space-evenly;
    padding: 100px 100px;
}
.outputs-wrapper div{

    height: 50px;
    width: 60px;
    background-color: white;
    border-radius: 5px;
    color:#fff;
    display:grid;
    padding: 30px 10px;
    box-shadow: 0 15px 20px rgba(0, 0, 0, 0.3);
}

.date1{
  padding: 220px 200px;
}

</style>

<script>
export default {
  data() {
    return {
      dt: new Date(),
    };
  },
  computed: {
    age() {
      const today = new Date();
      let age = today.getFullYear() - this.dt.getFullYear();
      const m = today.getMonth() - this.dt.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < this.dt.getDate())) {
        age = age - 1;
      }
      return age;
    },
    month(){
      const today = new Date();
      var m1 = this.dt.getMonth();
      var m2 = today.getMonth() ;
      var d1 = this.dt.getDate();
      var d2 = today.getDate();
      var month = [31,28,31,30,31,30,31,31,30,31,30,31];
      
      if(d1 > d2){
        d2 = d2 + month[m2 - 1];
        m2 = m2 - 1;
      }

      if(m1 > m2){
        m2 = m2 + 12;  
      }
      var m = m2 - m1 ;
      return m;
    },
    day(){
      const today = new Date();
      
      var m2 = today.getMonth() ;
      var d1 = this.dt.getDate();
      var d2 = today.getDate();
      var month = [31,28,31,30,31,30,31,31,30,31,30,31];
      if(d1 > d2){
        d2 = d2 + month[m2 - 1];
        m2 = m2 - 1;
      }
      var d = d2 - d1;
      return d;
  }
  }
};
</script>
