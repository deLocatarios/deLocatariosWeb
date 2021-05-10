<template>
    <div class="d-footer">
      <div class="d-container">
        <el-row type="flex" align="top" justify="center">
          <el-col :sm="10">
            <div class="footer-logo">
              <img src="~/assets/diseno/delocatarios/logo-normal.png" alt="">
            </div>
            <div class="text-footer">
              Únete a la comunidad de locatarios y aumenta tus ventas con posicionamiento en internet y redes sociales.
            </div>
          </el-col>
          <el-col :sm="12" :offset="2">
            <div class="text-subscription">
              <p class="title">Suscríbete</p>
              <p class="body">¿Te interesa formar parte de la comunidad digital con mayor potencial EnXona? Suscríbete y nos pondremos en contacto contigo</p>
              <el-row>
                <el-col :sm="19">
                  <el-input placeholder="Ingresa tu correo" v-model="subscription_email" clearable></el-input>
                </el-col>
                <el-col :sm="5">
                  <el-button type="primary">Suscríbirme</el-button>
                </el-col>
              </el-row>
            </div>
          </el-col>
        </el-row>
      </div>
    </div>
</template>

<script>
    export default {
        name: "Footer",
      data(){
          return{
            subscription_email: ""
          }
      }
    }
</script>

<style lang="scss">
  .d-footer{
    padding: 50px 0;
    background-color: lighten($gray, 5);
    border-top: 1px solid lighten($gray-text, 40%);
    .footer-logo{
      img{
        max-width: 180px;
      }
    }
    .text-footer{
      padding: 30px 0;
      font-size: 16px;
      color: $gray-text;
      font-weight: lighter;
      line-height: 20px;
    }
    .text-subscription{
      .title{
        font-size: 25px;
        font-weight: bold;
        color: $purple;
        padding: 15px 0;
      }
      .body{
        color: $gray-text;
        padding: 15px 0;
        font-weight: lighter;
        line-height: 20px;
      }
    }
  }
</style>
