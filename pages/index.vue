<template>
  
  <div id="app">
    <Conversor moeda-a="USD" moeda-b="BRL"/>
    <Conversor moeda-a="CAD" moeda-b="BRL"/>



  </div>


</template>
</template>

<script>
import Conversor from '@/components/conversor.vue';
  export default {
    components: {
      Conversor
    }

  };
  
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  margin-top: 10px;
  color: rgb(2, 2, 20);

}

</style>
