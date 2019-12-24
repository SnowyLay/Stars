<template>
  <div>
     <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
      style="height:200px"
    >
    <block v-for="item in imgUrls" :key="item">
      <swiper-item>
        <image :src="item" style="width:100%;"/>
      </swiper-item>
    </block>
  </swiper>
  <i-panel title="成员简介">
    <view style="padding: 15px;">
      <i-card i-class="split" title="李汶翰" thumb="/static/images/李汶翰.jpg">
        <view slot="content">中国流行乐男歌手、演员、主持人，男子演唱组合UNIQ成员、UNINE队长。</view>
        <view slot="footer">生日：1994年7月22</view>
      </i-card>
      <i-card i-class="split" title="王一博" thumb="/static/images/王一博.jpg"">
        <view slot="content">中国流行乐男歌手、演员、主持人，男子演唱组合UNIQ成员，职业摩托车赛车手。</view>
        <view slot="footer">生日：1997年8月5日</view>
      </i-card>
      <i-card i-class="split" title="曹承衍" thumb="/static/images/曹承衍.jpg">
        <view slot="content">韩国流行乐男歌手，中韩男子演唱组合UNIQ、韩国限定男子演唱组合X1成员。</view>
        <view slot="footer">生日：1996年8月5日</view>
      </i-card>
      <i-card i-class="split" title="金圣柱" thumb="/static/images/金圣柱.jpg">
        <view slot="content">亚洲偶像团体UNIQ成员。</view>
        <view slot="footer">生日：1994年2月16日</view>
      </i-card>
      <i-card i-class="split" title="周艺轩" thumb="/static/images/周艺轩.jpg">
        <view slot="content">中国内地流行乐男歌手、影视演员，男子演唱组合UNIQ队长。</view>
        <view slot="footer">生日：1990年12月11</view>
      </i-card>
    </view>
  </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      imgUrls: [
        '/static/images/团体照3.jpg',
        '/static/images/团体照4.jpg',
        '/static/images/团体照1.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
    }
  },


  methods: {
    },
   

  created () {
  }
}
</script>

<style scoped>
</style>
