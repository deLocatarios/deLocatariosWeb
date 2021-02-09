<template>
    <div class="bg-white-cover">
      <div class="d-container">
        <div class="commerce-list">
          <h1 class="title-commerce">Los mejores <span class="purple">comercios cercanos</span> a ti te esperan</h1>
          <no-ssr>
            <div class="only-slider">
              <slick-slide
                ref="slick"
                :options="slickOptions">
                <div class="commerce" v-for="commerce in commerces">
                  <div class="commerce-bg" :style="{ backgroundImage: `url(${commerce_demo_img})` }">
                    <div class="commerce-logo" :style="{ backgroundImage: `url(${commerce_demo_logo})` }"></div>
                  </div>
                  <div class="commerce-products">
                    <el-row type="flex" align="middle">
                      <el-col span="8"><div class="product" :style="{ backgroundImage: `url(${commerce_demo_logo})` }"></div></el-col>
                      <el-col span="8"><div class="product" :style="{ backgroundImage: `url(${commerce_demo_logo})` }"></div></el-col>
                      <el-col span="8"><div class="product" :style="{ backgroundImage: `url(${commerce_demo_logo})` }"></div></el-col>
                    </el-row>
                  </div>
                  <div class="commerce-url">
                    <el-link type="primary">Visitar la tienda <i class="el-icon-arrow-right el-icon--right"></i></el-link>
                  </div>
                </div>
              </slick-slide>
              <div v-if="commerces.length > 4">
                <div class="before-row slider-rows" @click="prev"></div>
                <div class="after-row slider-rows" @click="next"></div>
              </div>
            </div>
          </no-ssr>
        </div>
      </div>
    </div>
</template>

<script>
  import commerce_demo_img from '~/assets/diseno/commerce/comercio.png';
  import commerce_demo_logo from '~/assets/diseno/commerce/logo_comercio.png';
  export default {
    name: "CommerceList",
    props: {
      commerces: Array
    },
    data: function () {
      return {
        commerce_demo_img,
        commerce_demo_logo,
        slickOptions: {
          arrows: false,
          dots: false,
          fade: false,
          speed: 1500,
          autoplaySpeed: 5000,
          slidesToShow: 4,
          slidesToScroll: 3,
        }
      }
    },
    methods: {
      next() {
        this.$refs.slick.next();
      },

      prev() {
        this.$refs.slick.prev();
      }
    }
  }
</script>

<style lang="scss">
  @import 'node_modules/slick-carousel/slick/slick.css';

  .only-slider{
    position: relative;
    .slider-rows{
      width: 50px;
      height: 50px;
      background-color: $purple;
      border-radius: 50px;
      position: absolute;
      bottom: 50%;
      cursor: pointer;
      opacity: .7;
      transition: all .5s ease-in;
      &:hover{
        opacity: 1;
      }
      &::before{
        content: "";
        font-family: element-icons !important;
        font-size: 15px;
        z-index: 10;
        position: absolute;
        top: 50%;
        left: 50%;
        margin-top: -7px;
        margin-left: -7px;
        color: white;
      }
      &.after-row{
        right: -15px;
        &::before{
          content: "\e6e0";
        }
      }
      &.before-row{
        left: -15px;
        &::before{
          content: "\e6de";
        }
      }
    }
  }

  .bg-white-cover{
    background-color: $white-cover;
  }
  .commerce-list{
    padding: 20px 0;
    .slick-slider{
      .slick-list{
        padding: 25px 0;
      }
    }
    .slick-initialized .slick-slide{
      padding: 10px;
    }
    .title-commerce{
      padding: 50px 0;
      font-size: 25px;
      font-weight: lighter;
    }
    .commerce{
      position: relative;
      box-shadow: 0 12px 17px -11px rgba(0,0,0,0.4);
      max-height: 100%;
      border-radius: 15px;
      .commerce-bg{
        height: 150px;
        width: 100%;
        background-size: cover;
        border-radius: 15px 15px 0 0;
        position: relative;
      }
      .commerce-logo{
        background-size: cover;
        border: solid 1px $gray;
        border-radius: 15px;
        box-shadow: 0px 12px 17px -11px rgba(0,0,0,0.4);
        bottom: -35px;
        padding: 5px;
        position: absolute;
        margin-left: -35px;
        width: 70px;
        height: 70px;
        left: 50%;
        z-index: 2;
      }
      .commerce-products{
        padding: 70px 0px 25px 25px;
        .product{
          background-size: cover;
          border: solid 1px $gray;
          border-radius: 15px;
          box-shadow: 0px 12px 17px -11px rgba(0,0,0,0.4);
          width: 70px;
          height: 70px;
        }
      }
      .commerce-url{
        padding: 15px;
        text-align: center;
      }
    }
  }
</style>
