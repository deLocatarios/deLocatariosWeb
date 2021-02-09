<template>
    <div class="bg-white-cover">
      <div class="d-container">
        <div class="coupon-list">
          <h1 class="title-coupon">Comercios con grandes <span class="purple">descuentos</span> para ti.</h1>
          <no-ssr>
            <div class="only-slider">
              <slick-slide
                ref="slick"
                :options="slickOptions">
                <div class="coupon" v-for="coupon in coupons">
                  <div class="coupon-body">
                    <el-row>
                      <el-col :sm="10">
                        <div class="coupon-bg" :style="{ backgroundImage: `url(${coupon_demo_img})` }"></div>
                      </el-col>
                      <el-col :sm="14">
                        <div class="coupon-content">
                          <div class="coupon-logo">
                            <img src="~/assets/diseno/coupons/logo.png" alt="">
                          </div>
                          <div class="coupon-text">
                            HASTA 15% DE AHORRO EN CALENTADORES SOLARES
                          </div>
                          <div class="coupon-btn">
                            <el-button class="btn-yellow" round>Visitar y localizar</el-button>
                          </div>
                        </div>
                      </el-col>
                    </el-row>
                  </div>
                </div>
              </slick-slide>
            </div>
          </no-ssr>
        </div>
      </div>
    </div>
</template>

<script>
  import coupon_demo_img from '~/assets/diseno/coupons/coupon1.png';
  import coupon_demo_logo from '~/assets/diseno/commerce/logo_comercio.png';
  export default {
    name: "couponList",
    props: {
      coupons: Array
    },
    data: function () {
      return {
        coupon_demo_img,
        coupon_demo_logo,
        slickOptions: {
          arrows: false,
          dots: false,
          fade: false,
          speed: 1500,
          autoplay: true,
          autoplaySpeed: 5000,
          slidesToShow: 2,
          slidesToScroll: 1,
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
  .coupon-list{
    padding: 20px 0;
    .slick-slider{
      .slick-list{
        padding: 25px 0;
      }
    }
    .slick-initialized .slick-slide{
      padding: 10px;
    }
    .title-coupon{
      padding: 50px 0;
      font-size: 25px;
      font-weight: lighter;
    }
    .coupon{
      position: relative;
      box-shadow: 0 12px 17px -11px rgba(0,0,0,0.4);
      max-height: 100%;
      border-radius: 10px;
      background-color: $yellow-dark;
      .coupon-body{
        margin: 15px;
        border-radius: 10px;
        background-color: $white;
      }
      .coupon-bg{
        height: 250px;
        width: 100%;
      }
      .coupon-content{
        padding: 15px;
        .coupon-logo{
          max-height: 150px;
        }
        .coupon-text{
          padding: 15px;
          font-size: 20px;
          max-width: 100%;
          height: 60px;
          max-height: 100%;
        }
        .coupon-btn{
          padding: 15px 0;
          .el-button{
            background-color: $yellow-dark;
          }
        }
      }
    }
  }
</style>
