<template>
  <div id="box">
    <Conversor :moeda-a="moeda" moeda-b="BRL"/>
  </div>
</template>

<script>
import Conversor from '@/components/conversor.vue';

export default {  
    name: "Banner",



    components: {
        Conversor
      
    },


    data(){
        return {

      moeda:""
        }
    }
    }
</script>


<style scoped>
@import url('https://fonts.googleapis.com/css?family=Roboto+Condensed');

  #box {
    background-image: url('~/assets/img/background.png');
    background-size: cover;
    padding: 50px;
    box-shadow: 0 30px 15px 0 rgba(0, 0, 0, 5.2);  
    background-color: rgb(207, 207, 207);
    display: inline-flex;

  }
</style> 

