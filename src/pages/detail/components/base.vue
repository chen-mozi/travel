<template>
  <div class="base">
    <div class="base-left">
      <div class="grade">
        <span class="grade-number">4.8</span>
        <span class="grade-score">分</span>
        <span class="grade-desc">很棒</span>
      </div>
      <div class="comment">525条评论</div>
    </div>
    <div class="base-right">
      <div class="title">景点简介</div>
      <div class="info">开放时间、贴士</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailBase'
}
</script>

<style lang="stylus" scoped>
  .base
    position: relative
    top: -.1rem
    padding: .2rem .2rem 0 .2rem
    padding-bottom: .2rem
    background: #FFFFFF
    border-radius: .1rem .1rem 0 0
    overflow: hidden
    border-bottom: 0.15rem solid #eee
    .base-left
      width: 50%
      float: left
      border-right: 0.01rem solid #EEEEEE
      .grade
        color: #ff8300
        .grade-number
          font-size: .44rem
          line-height: .44rem
        .grade-score
          font-size: .28rem
          margin-left: -0.08rem
        .grade-desc
          font-size: .28rem
          line-height: .48rem
          margin-left: .2rem
      .comment
        font-size: .24rem
        color: #9e9e9e
        line-height: .32rem
        margin-right: .2rem
    .base-right
      float: left
      padding-left: .3rem
      .title
        font-size: .28rem
        color: #212121
        line-height: .48rem
      .info
        color: #9e9e9e
        font-size: .24rem

</style>
