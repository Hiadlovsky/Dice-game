<template>
    <div class="die__display__position container">
        <a @click="rollDice"  href="#"> <img class="butto_roll" src="../../images/roll_button.png" alt="roll_button"></a>
        <template v-if="show">
            <div v-for="(item, index) in this.data.playingRole" :key="index">
                <img class="die" :class="'die'+index" :src="link(index, data.playingRole)" alt="die">
            </div>   
        </template>
    </div>
</template>

<script>
export default {
    data(){
        return{
            show: false,
            
        }
    },
    props:[
        'data'
    ],
    methods: {
        link(index, array){

            return  '../../images/'+array[index]+'.png';
        },
         randomNumber(){
           let a = Math.floor(Math.random()*6)+1;
            return a;
       },
       rollDice(){
           this.show= true;
           this.data.rollSound.play();
           for (let i = 0; i < 7; i++) {
            setTimeout(() => {
                //function
                 this.data.playingRole.forEach((el,index) =>{
                        this.$set(this.data.playingRole,index,this.randomNumber());
                    console.log(this.show);
                });     
                console.log("Test");
             }, 300 * i);
            }

          setTimeout(() =>{
              this.show= false
              this.data.playerOne.score = this.data.playingRole;
              },5000);
      
       },
       test(){
           console.log('test');
       },
    }    
    
}
</script>

<style lang="scss">
    .die{
        border-radius: 16%;
        width: 2%;
     
    }

    .die0{
        position: absolute;
        left: 34%;
        top: 30%;
    }
    .die1{
        position: absolute;
        left: 44%;
        top: 45%;
    }
    .die2{
        position: absolute;
        left: 48%;
        top: 32%;
    }
    .die3{
        position: absolute;
        left: 50%;
        top: 50%;
    }
    .die4{
        position: absolute;
        left: 60%;
        top: 45%;
    }
    .butto_roll{
        margin: 20px;
        border-radius: 60px;
        width: 6%;
    }
    
</style>