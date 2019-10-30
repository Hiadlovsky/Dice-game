<template>
  <div id="app" class="container">
    		<footer class="app-footer px-1">
            <div>
              <a href="https://www.linkedin.com/in/pavol-hiadlovsky-154966184/">Pavol Hiadlovsky</a>
              <span>&copy; 2019 Hiadlovsky.</span>
            </div>
            <div class="ml-auto">
              <span>Graphic from</span>
              <a href="https://thewitcher.com/en/witcher1">WITCHER 1</a>
            </div>
        </footer>

    
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
     
    }
  }
}
</script>

<style lang="scss">
  body{
   font-family: Arial, Helvetica, sans-serif;   
  }
  .app-footer{
    background-color: rgb(118, 142, 209);
    div{
      padding-left: 5px;
    }
   
    a{
       text-decoration: none;
       color: rgb(179, 181, 184);
       &:hover{
         color: rgb(29, 100, 105);
       }
       
    }
  }


</style>
