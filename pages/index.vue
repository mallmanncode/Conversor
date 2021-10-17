<template>
  
  <div id="app">
    <Banner />
  </div>
  

</template>

<script>
import Banner from '@/components/banner.vue'
  export default {
    components: {
      Banner
    },
  };
  
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  display: flex;
  color: rgb(2, 2, 20);
}
</style>