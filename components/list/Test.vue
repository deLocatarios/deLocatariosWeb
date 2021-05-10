<template>
    <div>
      <div  class="myCard" :class="color">
        <img src="~/assets/diseno/delocatarios/location.png" alt="">
        <p>{{ my_text }}</p>
      </div>
    </div>
</template>

<script>
    export default {
      name: "Test",
      props: ['my_text', 'color']
    }
</script>

<style lang="scss">
  .myCard{
    text-align: center;
    img{
      width: 100px;
      margin: 0px auto;
    }
    p{
      padding: 15px;
    }
    &.red{
      p{
        color: red ;
      }
    }
    &.blue{
      p{
        color: blue ;
      }
    }
  }
</style>
