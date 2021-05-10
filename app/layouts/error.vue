<template>
  <div class="error-layout">
    <div v-if="error.statusCode === 404">
      <el-row>
        <el-col :span="24">
          <div class="logo-error">
            <p>No encontramos la página</p>
            <img src="~/assets/diseno/delocatarios/error.png" alt="">
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['error'],
  }
</script>

<style lang="scss">
  .error-layout{
    width: 100%;
  }
  .logo-error{
    padding: 10% 0;
    text-align: center;
    vertical-align: center;
    p{
      font-size: 2rem;
      padding: 25px 0;
    }
    img{
      width: 100%;
      max-width: 350px;
    }
  }
</style>
