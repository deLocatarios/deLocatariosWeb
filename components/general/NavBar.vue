<template>
  <div class="d-NavBar">
    <div class="d-container">
      <el-row type="flex" justify="center" align="middle">
        <el-col :sm="5">
          <div class="d-logo">
            <img src="~/assets/diseno/delocatarios/logotipo-web.png" alt="">
          </div>
        </el-col>
        <el-col :sm="13">
          <div class="d-input-search">
            <el-input
              class="d-input"
              placeholder="Busca comida, tiendas, hoteles, salud y más..."
              suffix-icon="el-icon-search"
              v-model="search">
            </el-input>
          </div>
          <div class="d-menu-line">
            <el-row>
              <el-col :sm="4">Inicio</el-col>
              <el-col :sm="6">
                <el-dropdown>
                  <span class="el-dropdown-link">
                    Categorías<i class="el-icon-arrow-down el-icon--right"></i>
                  </span>
                  <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item>Hospedaje</el-dropdown-item>
                    <el-dropdown-item>Comida</el-dropdown-item>
                    <el-dropdown-item>Tiendas y Supermercados</el-dropdown-item>
                  </el-dropdown-menu>
                </el-dropdown>
              </el-col>
              <el-col :sm="4">Promociones</el-col>
              <el-col :sm="4">Contacto</el-col>
              <el-col :sm="4">Ayuda</el-col>
            </el-row>
          </div>
        </el-col>
        <el-col :sm="6">
          <div class="d-buttons">
            <el-button class="btn-yellow" size="small" round>Registrarse</el-button>
            <el-button class="btn-login" type="text">Iniciar Sesión</el-button>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
    export default {
      name: "NavBar",
      data(){
        return{
          search: ""
        }
      }
    }
</script>

<style lang="scss">
  .d-NavBar{
    max-width: 100%;
    background: linear-gradient($purple, lighten($purple, 8));
    padding: 15px;

    .d-buttons{
      text-align: right;
      .el-button{
        padding-left: 20px;
      }
      .btn-yellow{
        background-color: $yellow;
        color: $black;
      }
      .btn-login{
        color: $white;
      }
    }
    .d-input-search{
      text-align: center;
      .d-input{
        .el-input__inner{
          border-radius: 15px;
          &::placeholder{
            color: lighten($black,.5);
          }
        }
      }
    }
    .d-menu-line{
      padding-top: 25px;
      padding-bottom: 10px;
      color: $white;
      text-align: center;
      font-size: 14px;
      .el-dropdown{
        color: $white;
      }
    }
    .d-logo img{
      max-width: 180px;
    }

  }
</style>
