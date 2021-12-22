<template>
  <swiper :slides-per-view="3" :space-between="50" @swiper="onSwiper" @slideChange="onSlideChange">
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
  </swiper>
</template>
<script>
  // Import Swiper Vue.js components
  import { Swiper as SwiperClass } from 'swiper/core';
  import getAwesomeSwiper from 'vue-awesome-swiper/dist/exporter'
  // SwiperClass.use([Pagination, Mousewheel, Navigation, Autoplay])
  const {Swiper, SwiperSlide, directive} = getAwesomeSwiper(SwiperClass)

  import 'swiper/swiper-bundle.min.css'

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    directives: {
      swiper: directive
    },
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
      };
    },
  };
</script>