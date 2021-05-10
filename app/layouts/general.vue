<template>
  <div>
    <NavBar></NavBar>
    <Nuxt />
  </div>
</template>

<script>
  import NavBar from "../components/general/NavBar";

  export default {
    components: {
      'NavBar': NavBar
    }
  }
</script>
