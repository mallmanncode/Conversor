<template>
  <div class="app">
    <section>
          <div class="nav">
        <Navbar />
        </div>
        <Nuxt />
        <div>
        <Footer />
        </div>
    </section>

  </div>
  
</template>

<script>
import Navbar from '@/components/navbar.vue'
import Footer from '@/components/footer.vue'

export default {

  components: {
    Navbar,
    Footer
  }
}

</script>

<style scoped>

#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: rgb(2, 2, 20);
  justify-content: space-between;

}

.nav {
      box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 9.2);  
      display: center;
      max-width: 500px;
      margin-left: auto;
      margin-right: auto;
      
}
</style>
