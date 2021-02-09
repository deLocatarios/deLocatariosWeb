<template>
    <div class="bg-white-cover">
      <div class="d-container">
        <div class="offer-list">
          <h1 class="title-offer"><span class="purple">OFERTAS</span> que podrían interesarte.</h1>
          <no-ssr>
            <div class="only-slider">
              <slick-slide
                ref="slick-offers"
                :options="slickOptions">
                <div class="offer" v-for="offer in offers">
                  <div class="offer-logo">
                    <img src="~/assets/diseno/offer/logo.png" alt="">
                  </div>
                  <div class="offer-content">
                    HASTA 15% EN CALENTADORES SOLARES
                  </div>
                  <div class="offer-product">
                    <img src="~/assets/diseno/offer/coupon1.png" alt="">
                  </div>
                  <div class="offer-btn">
                    <el-button class="btn-yellow" round>Visitar y localizar</el-button>
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
  import offer_demo_img from '~/assets/diseno/offer/coupon1.png';
  import offer_demo_logo from '~/assets/diseno/offer/logo.png';
  export default {
    name: "OfferList",
    props: {
      offers: Array
    },
    data: function () {
      return {
        offer_demo_img,
        offer_demo_logo,
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
  .offer-list{
    padding: 20px 0;
    .slick-slider{
      .slick-list{
        padding: 25px 0;
      }
    }
    .slick-initialized .slick-slide{
      padding: 10px;
    }
    .title-offer{
      padding: 50px 0;
      font-size: 25px;
      font-weight: lighter;
    }
    .offer{
      position: relative;
      box-shadow: 0 12px 17px -11px rgba(0,0,0,0.4);
      max-height: 100%;
      border-radius: 15px;
      background-color: $white;
      // padding: 30px;
      .offer-logo{
        padding: 30px 0;
        text-align: center;
        width: 100%;
        img{
          max-height: 100px;
          margin: 0px auto;
        }
      }
      .offer-content{
        padding: 20px;
        font-size: 22px;
        font-weight: bold;
        line-height: 25px;
        max-width: 100%;
        height: 90px;
        max-height: 100%;
        color: darken($gray, 50);
        text-align: center;
      }
      .offer-product{
        width: 100%;
        img {
          margin: 0 auto;
          max-height: 150px;
        }
      }
      .offer-btn{
        padding: 15px 0;
        text-align: center;
        .el-button{
          background-color: $yellow-dark;
        }
      }
    }
  }
</style>
