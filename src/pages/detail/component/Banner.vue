<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg" alt="大连圣亚海洋世界(AAAA景区)">
      <div class="banner-info">
        <div class="banner-tittle">
          大连圣亚海洋世界(AAAA景区)
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          2
        </div>
      </div>
    </div>
    <fade-animation>
      <gallary v-show="showGallary"
               @close="handleGallaryClose"></gallary>
    </fade-animation>
  </div>
</template>

<script>
import Gallary from '../../../common/gallary/Gallary'
import FadeAnimation from '../../../common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  components: {
    Gallary,
    FadeAnimation
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="scss" scoped>
  .banner{
    position: relative;
    overflow: hidden;
    height: 0;
    padding-bottom: 55%;
    .banner-img{
      width: 100%;
    }
    .banner-info{
      display: flex;
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      line-height: .6rem;
      color: #fff;
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));
      .banner-tittle{
        flex: 1;
        font-size: .32rem;
        padding: 0 .2rem;
      }
      .banner-number{
        height: .32rem;
        line-height: .32rem;
        margin-top: .14rem;
        padding: 0 .4rem;
        border-radius: .2rem;
        background: rgba(0, 0, 0, .8);
        font-size: .24rem;
        .banner-icon{
          font-size: .24rem;
        }
      }
    }
  }
</style>
