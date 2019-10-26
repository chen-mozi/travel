<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :icons="iconList"></home-icons>
    <home-hot-recommend :hot="hotList"></home-hot-recommend>
    <home-love-list :love="loveList"></home-love-list>
    <home-weekend :weekend="weekendList"></home-weekend>
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
import axios from 'axios'
import {mapState} from 'vuex'
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
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      hotList: [],
      loveList: [],
      weekendList: []
    }
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city= ' + this.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.SwiperList
        this.iconList = data.iconList
        this.hotList = data.HotList
        this.loveList = data.LoveList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>

<style>
</style>
