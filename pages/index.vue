<template>
  <div>
    <Sliders></Sliders>
    <Search></Search>
    <CommerceList :commerces=commerces></CommerceList>
    <CouponList :coupons=commerces></CouponList>
    <OfferList :offers="commerces"></OfferList>
    <Banner></Banner>
    <Information></Information>
    <Footer></Footer>
  </div>
</template>

<script>
import Sliders from "../components/home/Sliders";
import Search from "../components/home/Search";
import CommerceList from "../components/home/CommerceList";
import CouponList from "../components/home/CouponList";
import OfferList from "../components/home/OfferList";
import Banner from "../components/home/Banner";
import Information from "../components/home/Information";
import Footer from "../components/general/Footer";

export default {
  components: [
    Sliders,
    Search,
    CommerceList,
    CouponList,
    OfferList,
    Banner,
    Information,
    Footer
  ],
  data(){
    return{
      commerces: ["oki", "doki", "oki", "doki", "oki", "doki"]
    }
  }
}
</script>


