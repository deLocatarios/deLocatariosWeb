<template>
    <div class="information">
      <div class="d-container">
        <el-row type="flex" justify="center" align="middle">
          <el-col>
            <div class="info-card">
              <img src="~/assets/diseno/information/location.png" alt="">
              <p>Encuentra los mejores lugares y servicios dentro de más de 20 Localidades que de Locatarios
                tiene para ti.</p>
            </div>
          </el-col>
          <el-col>
            <div class="info-card">
              <img src="~/assets/diseno/information/categories.png" alt="">
              <p>Contamos con 26 categorías hechas para ti. <br> ¡Encuentra lo que necesitas! </p>
            </div>
          </el-col>
          <el-col>
            <div class="info-card">
              <img src="~/assets/diseno/information/people.png" alt="">
              <p>Más de mil Usuarios visitan <span class="">deLocatarios.com</span></p>
            </div>
          </el-col>
        </el-row>
      </div>
    </div>
</template>

<script>
    export default {
        name: "Information"
    }
</script>

<style lang="scss">
  .information{
    padding-top: 30px;
    padding-bottom: 100px;
    .info-card{
      text-align: center;
      width: 240px;
      margin: 0px auto;
      font-weight: lighter;
      line-height: 20px;
      img{
        padding: 50px 0;
        max-height: 100px;
      }
      p{
        line-height: 25px;
        color: $gray-text;
      }
    }
  }
</style>
