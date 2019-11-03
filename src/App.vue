<template>
  <div id="app page-container" class="container">
    <div id="content-wrap">
      <dice-roll :data = "gameData"></dice-roll>
      <player-one :data = "gameData"></player-one>
    
    </div>
    		<footer class="app-footer px-1 navbar navbar-fixed-bottom">
          <div id="footer" >
            <div>
              <a href="https://www.linkedin.com/in/pavol-hiadlovsky-154966184/">Pavol Hiadlovsky</a>
              <span>&copy; 2019 Hiadlovsky.</span>
            </div>
            <div class="ml-auto">
              <span>Graphic from</span>
              <a href="https://thewitcher.com/en/witcher1">WITCHER 1</a>
            </div>
          </div>
        </footer>
        
         
  </div>
</template>

<script>
import diceRoll from './components/dice_roll.vue';
import playerOne from './components/player_one.vue';
export default {
  name: 'app',
  data () {
    return {
      gameData:{
        rollSound: new Audio('../sounds/Shake And Roll Dice-SoundBible.com-591494296.wav'),
        playingRole:[0,0,0,0,0],
        selected:[false, false, false, false, false],
        turn:0,
        playerOne:{
          score:[0,0,0,0,0],
          selected:[false, false, false, false, false],
        },
        playerTwo:{
          score:[0,0,0,0,0],
          selected:[false, false, false, false, false],
        }  
      }
     
    }
  },
  components:{
      'dice-roll': diceRoll,
      'player-one': playerOne, 

  }
}
</script>

<style lang="scss">
  body{
   color: rgb(213, 226, 226);
   font-family: Arial, Helvetica, sans-serif; 
   background-color: #E4B898;
   background-image: url('../images/background.png');
   background-repeat: no-repeat;
   -webkit-background-size:cover;
   -moz-background-size:cover;
   -o-background-size:cover;
   background-size:cover;
   background-color: #000;
  
  
  
  }
  .app-footer{
    background-color: rgb(118, 142, 209);
     position: absolute;
     bottom: 0;
     width: 68%;
    
    
    
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
