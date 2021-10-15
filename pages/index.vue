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
    }
  };
  
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: rgb(2, 2, 20);
  justify-content: space-between;
}
</style>