<template>
  <div>
    <p>{{ oki }}</p>
  </div>
</template>

<script>
  export default {
    data(){
      return{
        oki: process.env.backend
      }
    }
  }
</script>
