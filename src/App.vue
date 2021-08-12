<template>
  <div id="app">   
    <div id="background"> 
      <nav-bar/>
      <router-view/>
    </div>  
  </div>
</template>

<script>
import NavBar from '@/components/layout/NavBar'

export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
