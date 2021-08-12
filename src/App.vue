<template>
  <span>   
    <div id="background"> 
      <header>
        <nav-bar/>
      </header>
      <main>
        <router-view/>
      </main>
      <rodape/>
      
    </div>  
  </span>
</template>

<script>
import NavBar from '@/components/layout/NavBar'
import Rodape from '@/components/layout/Rodape'

export default {
  name: 'App',
  components: {
    NavBar,
    Rodape
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
