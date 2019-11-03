<template>
    <div>
        <template>
            <p>test</p>
            <div v-for="(item, index) in this.data.playerOne.score" :key="index">
                <a href="#"  @click="seteselectorArgument(index)">
                    <template v-if="!data.playerOne.selected[index]">
                        <img  class="die" :class="'die'+index+'PlayerOne'" :src="link(index, data.playerOne.score)" alt="die">
                    </template>
                     <template v-else>
                        <img  class="die" :class="'die'+index+'PlayerOne'" :src="selected(index, data.playerOne.score)" alt="die">
                    </template>
                </a>
            </div>   
        </template>
    </div>
</template>

<script>
export default {
    data(){
        return{
            test: false,
            playing: true,
        }
    },
    props:[
        'data'
    ],
    methods:{
        link(index, array){

            return  '../../images/'+array[index]+'.png';
        },
        selected(index, array){

            return  '../../images/'+array[index]+'_selected.png';
        },
        seteselectorArgument(i){
            if(this.playing){
                console.log('printed '+ i);
                //this.data.playerOne.selected[i] = !this.data.playerOne.selected[i];
                if ( this.data.playerOne.selected[i] == false) {
                    this.$set(this.data.playerOne.selected,i,true);            
               }
               else{
                   this.$set(this.data.playerOne.selected,i,false);
               }    
                console.log( this.data.playerOne.score[i]);
                console.log(this.data.playerOne.selected[i]);
            }
            this.data.selected= this.data.playerOne.selected;
        }
    }
    
}
</script>



<style lang="scss" scoped>

</style>