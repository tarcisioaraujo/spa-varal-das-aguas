<template>
  <div id="bgmenu">
    
    <nav class="navbar navbar-expand-lg" style="background-color: #005370;">            
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav" style="padding-left: 70px;">  
          <li class="nav-item">
            <a class="nav-link" href="\" style="color:#048cbc;">INÍCIO</a>
          </li> 
          <li class="nav-item">
            <a class="nav-link" href="#OCONCURSO" style="color:#048cbc;">O CONCURSO</a>
          </li>  
          <li class="nav-item">
            <a class="nav-link" href="#SOBRE" style="color:#048cbc;">SOBRE</a>
          </li>  
          <li class="nav-item">
            <a class="nav-link" href="#REGRAS" style="color:#048cbc;">REGRAS</a>
          </li>  
          <li class="nav-item">
            <a class="nav-link" href="#FAASUAINSCRIO" style="color:#048cbc;">INSCRIÇÃO</a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      
    }
  },
  mounted () {
    $('a.nav-link[href^="#"]').on('click', function(e) {     
      e.preventDefault();
      var id = $(this).attr('href'),
      targetOffset = $(id).offset().top;
        
      $('html, body').animate({ 
        scrollTop: targetOffset - 100
      }, 500);
    });
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
