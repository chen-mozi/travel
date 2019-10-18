<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-hot-recommend></home-hot-recommend>
    <home-love-list></home-love-list>
    <home-weekend></home-weekend>
    <home-footer></home-footer>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHotRecommend from './components/HotRecommend'
import HomeLoveList from './components/LoveList'
import HomeWeekend from './components/Weekend'
import HomeFooter from './components/Footer'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeHotRecommend,
    HomeLoveList,
    HomeWeekend,
    HomeFooter
  }
}
</script>

<style>
</style>
