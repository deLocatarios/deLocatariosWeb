<template>
    <div>
      <el-dialog
        :visible.sync="dialogVisible"
        width="30%"
        :before-close="handleClose">
        <div class="location-info">
          <img src="~/assets/diseno/delocatarios/location.png" alt="">
          <p>Bienvenid@, A partir de este momento te recomendaremos los mejores comercios de tu zona.</p>
        </div>
        <span slot="footer" class="dialog-footer">
          <el-button @click="dialogVisible = false">Cancelar</el-button>
          <el-button class="btn-purple" type="primary" @click="getLocation()">Confirmar</el-button>
        </span>
      </el-dialog>

    </div>
</template>

<script>
    export default {
      name: "LocationModal",
      props: ['currentLocation'],
      data(){
        return{
          dialogVisible: false
        }
      },
      mounted() {
        if (!localStorage.getItem('geolocation')){
          this.dialogVisible = true;
        }
        console.log(localStorage.getItem('geolocation'))
      },
      methods: {
        getLocation() {
          this.dialogVisible = false;
          navigator.geolocation.getCurrentPosition(
            position => {
              console.log(position.coords.latitude);
              console.log(position.coords.longitude);
              localStorage.setItem('geolocation', position.coords.latitude + ',' + position.coords.longitude);
            },
            error => {
              console.log(error.message);
            },
          )
        }
      }
    }
</script>

<style lang="scss">
  .location-info{
    max-width: 100%;
    text-align: center;
    word-break: normal;
    img{
      width: 100%;
      max-width: 200px;
    }
    p{
      padding: 15px 0;
      font-size: 16px;
    }
  }
</style>
