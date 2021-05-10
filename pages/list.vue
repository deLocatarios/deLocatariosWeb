<template>
  <div class="test">

    <el-row>
      <el-col :sm="8" v-for="commerce in commerces">
        <Test :my_text=commerce.text :color=commerce.color></Test>
      </el-col>
    </el-row>

  </div>
</template>

<script>

  import Test from "../components/list/Test";

  export default {
    components: [Test],
    data(){
      return{
        commerces: [{
          text: 'hola',
          color: "red"
        },
        {
          text: 'hola mundo',
          color: "blue"
        },
          {
            text: 'hola mundo',
            color: "blue"
          }]
      }
    },
    head(){
      return{
        title: "Listado - Delocatarios"
      }
    }
  }
</script>

<style lang="scss">
  .test{
    padding: 25px 10px 5px 12px;
  }

</style>


