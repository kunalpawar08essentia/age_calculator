<template>
<body>
    <div class="main">

        <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="250px" class="demo-ruleForm">
            <el-form-item >
                <label class="labelname" prop="name" style=" margin-left: -240px; font-size: 20px; color: white;">Name: </label>
                <el-input placeholder="Enter your name" class="inputname" v-model="enteredValue" v-on:keyup.enter="submit" ></el-input>
              </el-form-item>
            <el-button type="success" round class="submit" style="margin-left: 100px;" v-on:click="submit" >Submit</el-button>
        </el-form>
    <div class="head" style="margin-left:1300px; margin-top:-100px;">
      <h1 style="color: Green;" v-for="name in names" :key="name" class="list">Hello {{ name }}</h1>
      </div>      
    </div>
</body>
</template>

<style>

body{
    background: black;
}
.main .inputname{
  margin-top:30px;
  padding-left: 50px;
  width: 300px;
}



</style>

<script>

  export default {
    data() {  

    return {
   
      names: [],
      enteredValue: ''
    };
  },
  methods: {
    submit() {
      
      this.enteredValue = this.enteredValue.toUpperCase();
      this.names.push(this.enteredValue);
      this.enteredValue = '';
    }
  },
  
  

  }
    
  
</script>
