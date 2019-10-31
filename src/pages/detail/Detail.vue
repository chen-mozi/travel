<template>
  <div>
    <detail-banner
      :sightName="sightName"
      :bannerImg = "bannerImg"
      :bannerImgs = "gallaryImgs"
    >
    </detail-banner>
    <detail-header></detail-header>
    <detail-base></detail-base>
    <detail-recommend :recommend="recommend"></detail-recommend>
    <detail-list :list="list"></detail-list>
    <home-footer></home-footer>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailBase from './components/base'
import DetailRecommend from './components/Recommend'
import DetailList from './components/List'
import HomeFooter from '.././home/components/Footer'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailBase,
    DetailRecommend,
    DetailList,
    HomeFooter
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: [],
      recommend: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('./api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.hanldeDetailSucc)
    },
    hanldeDetailSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.list
        this.recommend = data.Recommend
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  scrollBehavior (to, from, savedPosition) {
    if (savedPosition) {
      return savedPosition
    } else {
      return { x: 0, y: 0 }
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
