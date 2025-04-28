<script setup>
    import { onMounted } from 'vue';
    import Swiper from 'swiper';
    import { Navigation, Pagination } from 'swiper/modules'; 
    import 'swiper/css/bundle';
    import 'swiper/css/navigation';
    import 'swiper/css/pagination';
    
    onMounted(() => {
      Swiper.use([Navigation, Pagination]);
      const swiper = new Swiper('.swiper', {
        speed: 1000,
        spaceBetween: 16,
        slidesPerView: 3,
        slidesPerGroup: 1,

        breakpoints: {
          320: {
            slidesPerView: 1,
          },
          768: {
            slidesPerView: 2,
          },
          1024: {
            slidesPerView: 3,
          },
        },

        // navigation
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },

        on: {
          init: function () {
            console.log('swiper initialized');
          },
        },
      });
      
    });

</script>

<template>
    <div class="swiper">
        <div class="swiper-wrapper">
            <div class="swiper-slide rounded-2xl">Slide 1</div>
            <div class="swiper-slide rounded-2xl">Slide 2</div>
            <div class="swiper-slide rounded-2xl">Slide 3</div>
            <div class="swiper-slide rounded-2xl">Slide 4</div>
            <div class="swiper-slide rounded-2xl">Slide 5</div>
            <div class="swiper-slide rounded-2xl">Slide 6</div>
        </div>


        <!-- Add Navigation -->
        <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
    </div>

</template>

<style>

.swiper {
  width: 100%;
  height: 100%; 
}

.swiper-slide {
  background: #eee;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  border: 1px solid #000;
  border-radius: 16px;
}
</style>