<template>
  <div>
    <Sliders></Sliders>
    {{ current_address }}
    <Search></Search>
    <CommerceList :commerces=commerces></CommerceList>
    <CouponList :coupons=commerces></CouponList>
    <OfferList :offers="commerces"></OfferList>
    <Banner></Banner>
    <Information></Information>
    <LocationModal></LocationModal>
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
import LocationModal from "../components/general/LocationModal";
import Test from "../components/list/Test";

export default {
  components: [
    Sliders,
    Search,
    CommerceList,
    CouponList,
    OfferList,
    Banner,
    Information,
    LocationModal,
    Test
  ],
  data(){
    return{
      commerces: ["oki", "doki", "oki", "doki", "oki", "doki"],
      current_address: ""
    }
  },
  head(){
    return{
      title: "Inicio - Delocatarios"
    }
  },
  mounted() {
    let current_location = localStorage.getItem('geolocation').split(',');
    let latitude = current_location[0];
    let longitude = current_location[1];
    // this.getStreetAddressFrom(latitude, longitude);
  },
  methods: {
    async getStreetAddressFrom(lat, long) {
      try {
        var { data } = await this.$axios.$get(
          "https://maps.googleapis.com/maps/api/geocode/json?latlng=" +
          lat +
          "," +
          long +
          "&key=AIzaSyBa_b2EjKlvpuMuIEPF2as3nf-R_Qyrd1c"
        );
        if(data.error_message) {
          console.log(data.error_message)
        } else {
          this.current_address = data.results[0].formatted_address;
        }
      } catch (error) {
        console.log(error.message);
      }
    }
  }
}
</script>


