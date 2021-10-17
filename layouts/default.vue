<template>
  <div class="app">
    <section>
          <div class="nav">
        <Navbar />
        </div>
        <Nuxt />
        <div class="foo">
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
  display: flex;
  color: rgb(2, 2, 20);
}
</style>
