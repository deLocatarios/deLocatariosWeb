<template>
    <div class="bg-gray">
      <div class="d-container">
        <el-row type="flex" align="middle" justify="center">
          <el-col :sm="12">
            <div class="container-search">
             <el-row type="flex" align="middle">
               <el-col :sm="8" :offset="2">
                 <div class="btn-search-dropdown">
                   <p class="title">Tu ubicación</p>
                   <el-select v-model="location" filterable placeholder="¿Donde buscar?">
                     <el-option
                       v-for="my_location in locations"
                       :key="my_location.key"
                       :value="my_location.value">
                     </el-option>
                   </el-select>
                 </div>
               </el-col>
               <el-col :sm="8" :offset="1">
                 <div class="btn-search-dropdown">
                   <p class="title">Categoría</p>
                   <el-select v-model="value" filterable placeholder="Busca una categoría">
                     <el-option
                       v-for="item in options"
                       :key="item.value"
                       :label="item.label"
                       :value="item.value">
                     </el-option>
                   </el-select>
                 </div>
               </el-col>
               <el-col :sm="4" style="text-align: center">
                 <div class="btn-search-dropdown">
                   <el-button class="btn-purple" icon="el-icon-search" circle></el-button>
                 </div>
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
        name: "Search",
      data(){
          return{
            location: "",
            locations: [
              {"key": "toluca", "value": "Toluca"},
              {"key": "temoaya", "value": "Temoaya"},
              {"key": "xonacatlan", "value": "Xonacatlán"},
              {"key": "villa-cuauhtemoc", "value": "Villa Cuauhtémoc"},
            ]
          }
      }
    }
</script>

<style lang="scss">
  .bg-gray{
    background-color: $gray;
  }
  .container-search{
    background-color: $white;
    margin: 40px 0;
    border-radius: 45px;
    .btn-search-dropdown{
      padding: 15px 0;
      .title{
        color: $black;
        padding-top: 15px;
        padding-left: 20px;
        font-size: 13px;
        font-weight: bold;
      }
      .el-dropdown-link{
        padding: 10px 0;
      }
      .el-select{
        input{
          border: 1px $white;
          &::placeholder{
            color: $blue;
          }
        }
      }
    }
    .el-button{
      background-color: $purple;
      color: white;
    }
  }
</style>
