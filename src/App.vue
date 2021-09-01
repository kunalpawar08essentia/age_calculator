<template>
  <div id="app">
    <name1/>
   <div id="dob1">
    <dob/>
  </div> 
  </div>
</template>

<script>
import name1 from './components/name1.vue'
import dob from './components/dob.vue'
export default {
  name: 'app',
  components: {
    name1,
    dob
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
