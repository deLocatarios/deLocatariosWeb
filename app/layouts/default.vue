<template>
  <div>
    <NavBar />
    <Nuxt />
    <Footer></Footer>
  </div>
</template>

<style>
</style>

<script>
  import NavBar from "../components/general/NavBar";
  import Footer from "../components/general/Footer";

  export default {
    components: [NavBar, Footer],
    head: function () {
      return {
        title: "Delocatarios"
      }
    }
  }
</script>
