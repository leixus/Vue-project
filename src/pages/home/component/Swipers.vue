<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'Swipers',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style scoped>
  .wrapper{
    overflow: hidden;
    width: 100%;
    height: 0;
    /*height: 26.66vm;*/
    padding-bottom: 31.25%;
    background: #ccc;
  }
  .wrapper >>> .swiper-pagination-bullet-active {
    background: #ffffff !important;
  }
  .swiper-img{
    width: 100%;
  }
</style>
