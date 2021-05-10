<template>
  <div class="sliders">
    <no-ssr>
      <slick-slide
        ref="slick"
        :options="slickOptions">
        <div class="slider" :style="{ backgroundImage: `url(${backgroundUrl})` }">
          <div class="slider-text">
            <p class="silder-title">¿Buscas algún banco, hotel florería o entretenimiento?</p>
            <p class="silder-description">¡Te ayudamos a encontrar los mejores comercios de la zona!</p>
          </div>
        </div>
        <div class="slider" :style="{ backgroundImage: `url(${backgroundUrl2})` }">
          <div class="slider-text">
            <p class="silder-title"></p>
            <p class="silder-description">Todo un UNIVERSO dedicado al comercio</p>
          </div>
        </div>
      </slick-slide>
    </no-ssr>
  </div>
</template>

<script>
  import backgroundUrl from '~/assets/diseno/portada.png';
  import backgroundUrl2 from '~/assets/diseno/portada2.png';
  export default {
    name: "Sliders",
    data: function () {
      return {
        backgroundUrl,
        backgroundUrl2,
        slickOptions: {
          arrows: false,
          dots: true,
          fade: false,
          speed: 1500,
          autoplaySpeed: 15000,
          autoplay: true,
          slidesToShow: 1,
          slidesToScroll: 1,
        }
      }
    }
  }
</script>

<style lang="scss">
  @import 'node_modules/slick-carousel/slick/slick.css';

  .sliders{
    width: 100%;
    .slider{
      width: 100%;
      height: 500px;
      background-size: cover;
      position: relative;
    }
    .slider-text{
      position: absolute;
      top: 25%;
      left: 50%;
      text-align: center;
      .silder-title{
        color: $white;
        font-size: 1.5rem;
        padding: 30px 15%;
      }
      .silder-description{
        color: $white;
        font-size: 2rem;
        font-weight: bold;
        padding: 30px 15%;
      }
    }
  }

  .slick-dots {
    display: flex;
    position: absolute;
    right: 30px;
    bottom: 0px;
    justify-content: center;

    margin: 0;
    padding: 1rem 0;

    list-style-type: none;

    li {
      margin: 0 0.25rem;
    }

    button {
      display: block;
      width: 40px;
      height: 8px;
      padding: 0;

      border: none;
      border-radius: 5px;
      background-color: $white;

      text-indent: -9999px;
      &:focus{
        outline: none;
        box-shadow: none;
      }
    }

    li.slick-active button {
      background-color: $purple;
    }

  }
</style>
