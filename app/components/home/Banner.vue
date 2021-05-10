<template>
    <div class="banner-background" :style="{ backgroundImage: `url(${commerce_demo_img})` }">
      <div class="d-container">
        <div class="banner-logo">
          <img src="~/assets/diseno/delocatarios/logotipo-web.png" alt="">
        </div>
        <el-row type="flex" justify="center" align="middle">
          <el-col :offset="12">
            <div class="text-banner">
              <h1>¿Tienes un negocio?</h1>
              <p>Anunciate y únete a la comunidad <span class="is-bold">de Locatarios</span>, posiciona tu marca y tu negocio hoy mismo.</p>
            </div>
            <div class="banner-btn">
              <el-button class="btn-purple" round>Registrarme</el-button>
            </div>
          </el-col>
        </el-row>
      </div>
    </div>
</template>

<script>
  import commerce_demo_img from '~/assets/diseno/anunciate/background.png';
  export default {
      name: "Banner",
    data(){
        return{
          commerce_demo_img
        }
    }
  }
</script>

<style lang="scss">
  .banner-background{
    background-size: cover;
    height: 300px;
    width: 100%;
    position: relative;
    .d-container{
      position: relative;
    }
    .text-banner{
      padding: 25px 15px;
      text-align: center;
      color: $white;
      h1{
        padding: 25px 0;
        font-size: 25px;
      }
      p{
        padding: 15px 0;
        font-size: 20px;
        font-weight: lighter;
      }
    }
    .banner-btn{
      text-align: center;
      .el-button{
        transition: all .5s ease-in;
        span{
          padding: 0px 15px;
        }
      }
    }
  }
  .banner-logo{
    position: absolute;
    top: 15px;
    left: 15px;
    img{
      max-width: 180px;
    }
  }
</style>
