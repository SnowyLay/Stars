<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>
    <i-panel title="我是粉丝，我要安利！！！">
      <i-input :value="name" @change="changeName($event)" title="作品名称" autofocus placeholder="请输入作品名称" maxlength="20" />
      <i-input :value="time" @change="changeTime($event)" title="发行时间" placeholder="请输入发行时间" maxlength="30" />
      <i-input :value="reason" @change="changeReason($event)" title="推荐理由" placeholder="请输入推荐理由" maxlength="50" />
    </i-panel>
    <i-button @click="handleClick" type="warning" size="default">我要推荐</i-button>
    <view class="tips">UNIQ粉丝Unicorn专用小程序，如果你有喜欢的作品请分享给大家！！！</view>
  </div>
</template>

<script>
export default {
  data () {
    return {
      name:"",
      time:"",
      reason:""
    }
  },
  methods: {
    changeName (event) {
      this.name = event.mp.detail.detail.value
    },
    changeReason (event) {
      this.reason = event.mp.detail.detail.value
    },
    changeTime (event) {
      this.time = event.mp.detail.detail.value
    },
    handleClick () {
      if (this.name && this.reason && this.time) {
        wx.showToast({
          title: '推荐了' + this.name,
          icon: 'success',
          duration: 2000
        })
        // TODO:将推荐数据提交到云数据库
      } else {
        wx.showToast({
          title: '信息不完整',
          icon: 'none',
          duration: 2000
        })
      }
    }
  },
  created () {
  }
}
</script>

<style scoped>
.userinfo {
  position: relative;
  width: 750rpx;
  height: 320rpx;
  color: #c078ff;
  display: flex;
  flex-direction: column;
  align-items: center;
}
 
.userinfo-avatar {
  overflow:hidden;
  display: block;
  width: 160rpx;
  height: 160rpx;
  margin: 20rpx;
  margin-top: 50rpx;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}
.tips {
  padding: 20pt;
  font-size: 10pt;
  color:#c078ff;
}
</style>
