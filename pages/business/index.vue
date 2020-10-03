<template>
  <div>
    <p>{{ oki }}</p>
  </div>
</template>

<script>
  export default {
    data(){
      return{
        oki: process.env.URL_BACKEND
      }
    }
  }
</script>
