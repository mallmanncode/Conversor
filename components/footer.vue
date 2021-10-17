<template>
  <div id="box" >
  <h1> Um sitema </h1>
  <a :href="'http://localhost:3000/'"> Lirio Code </a>
  <h1> @2021 </h1>
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
    box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 5.2);  
    padding: 5px;
}

h1 {
    display: inline-flex;
    padding-inline: 10px;
    color: rgb(136, 136, 136);
}
a {
    color: rgb(202, 216, 255);
}

a:hover {
    color: rgb(255, 0, 0);
}

</style>