<template>
  <div id="main-banner">
    <Conversor :moeda-a="this.moeda" moeda-b="BRL"/>
  </div>
</template>

<script>
import Conversor from '@/components/conversor.vue';

export default {  
    name: "Banner",

    data(){
        return {

      moeda:""
        }
    },



    components: {
        Conversor
    }
    }
</script>


<style scoped>
  #main-banner {
    background-image: url('~/assets/img/background.png');
    background-position: 0 -250px;
    background-size: cover;
    height: 100%;
    align-items: center;
    justify-content: center;
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
    color: rgb(2, 2, 20);
    padding: 20px 40px;
    width: 100%;
    box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 5.2);  

  }
</style>