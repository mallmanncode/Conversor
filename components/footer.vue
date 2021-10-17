<template>
  <div id="box" >
      <div class="texto">
  <h1> Um sitema 
  <a :href="'http://localhost:3000/'"> Lirio Code </a>
   @2021 </h1>
  </div>
  </div>
</template>

<script>

export default {  
    name: "Footer",
    }
</script>


<style scoped>
  #box {
    background-color: rgb(0, 110, 255);
    text-align: center;
    box-shadow: 0 20px 15px 0 rgba(0, 0, 0, 5.2); 
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
 }
h1 {
    padding-inline: 10px;
    color: rgb(190, 190, 190);
}
a {
    color: rgb(83, 86, 255);
}

a:hover {
    color: rgb(255, 0, 0);
}

</style>