<template>
  <div>
    <view class="userinfo">
        <view class="userinfo-avatar">
        <open-data type="userAvatarUrl"></open-data>
        </view>
        <view class="userinfo-name">
        <open-data type="userNickName"></open-data>
        </view>
    </view>






    <i-cell-group>
    <i-cell title="我的收藏" is-link url="/pages/kefu/main"> </i-cell>

    <i-cell title="我的小象" is-link url="/pages/kefu/main"> </i-cell>

    <i-cell title="我的客服" is-link url="/pages/kefu/main"> </i-cell>
    
    <i-cell title="关于我们" is-link url="/pages/order/main"> </i-cell>
  
    <i-cell title="设置" is-link url="/pages/money/main"></i-cell>
 
</i-cell-group>
  </div>
</template>

<script>
import card from '@/components/card'
export default {
  data () {
    return {
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },
  components: {
    card
  },
  methods: {
    
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    }
  },
  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
.userinfo {
  position: relative;
  background-color: #50b7c1;
  width: 750rpx;
  height: 280rpx;
  display: flex;
  flex-direction: column;
  align-items: left;
}
 
.userinfo-avatar {
  position: left;
  overflow:hidden;
  display: flex;
  width: 130rpx;
  height: 130rpx;
  margin: 20rpx;
  margin-top: 20rpx;
  border-radius: 50%;
  border: 2px solid #fff;
}


</style>