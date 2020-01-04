<template>
   <div>
   <view class='page_row' bindtap="suo">
   <view class="search">  

<view class="df search_arr">
  <icon class="searchcion" size='16' type='search'></icon>
   
					
  <input class="input" placeholder-class="place-holder" placeholder="请输入关键字" bindinput='listenerSearchInput' bindconfirm="toSearch" />
</view>
   </view>
    <view class='sousuo'>搜索</view> 
 </view> 

  
 <i-tabs :current="current_scroll" scroll @change="handleChangeScroll">
    <i-tab key="tab1" title="考古发现"></i-tab>
    <i-tab key="tab2" title="宇宙奥秘"></i-tab>
    <i-tab key="tab3" title="灵异未知"></i-tab>
    <i-tab key="tab4" title="航空航天"></i-tab>
    <i-tab key="tab5" title="文化艺术"></i-tab>
    <i-tab key="tab6" title="刑侦案件"></i-tab>
    <i-tab key="tab7" title="灾难"></i-tab>
    <i-tab key="tab8" title="动物"></i-tab>
    <i-tab key="tab9" title="体育"></i-tab>
</i-tabs>
    <i-panel title="高分推荐">
    <view style="padding: 10px;">
        <i-card i-class="split" title="我们诞生在中国" thumb="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575454117478&di=26037fee3b4a03851e52878076a7291c&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201607%2F20%2F20160720141506_aBjsU.thumb.700_0.jpeg">
        <view slot="content">栖息于四川竹林的大熊猫、隐居于雪域高原的雪豹、攀缘于神农架的金丝猴这三个中国独有的野生动物家庭里动物宝宝们各自出生、成长的感人故事。</view>
        <view slot="footer">陆川</view>
        </i-card>
    </view>
    </i-panel>
    <i-panel title="猜你喜欢">
        <view style="padding: 10px;">
        <i-card i-class="split" title="不惧风暴" thumb="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575454243632&di=5cc942c0924636a567b1ca0ea8d2faec&imgtype=0&src=http%3A%2F%2Fwww.sinaimg.cn%2Fent%2Fr%2Fm%2F2014-09-18%2FU4611P28T3D4211166F326DT20140918094514.jpg">
        <view slot="content">该片讲述了一场史无前例的EF6飓级风突袭美国小镇制造大灾难的故事。故事围绕着同一小镇的三组人物展开，并通过各自的视角真实还原EF6级飓风惊人的破坏力。</view>
        <view slot="footer">（美）斯蒂文-奎里</view>
        </i-card>
    </view>
    </i-panel>
      <view class="top-padding"></view>
     </div>
</template>

<script>
import card from '@/components/card'
export default {
  data () {
    return {
    
     
       current_scroll:'tabl',
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
    handleChangeScroll(detail){
      console.log(detail)
      this.current_scroll = detail.mp.detail.key
      }
    },
    handleChange ({ detail }) {
        this.setData({
            current: detail.key
        });
    },
    handleChangeScroll (event) {
        this.current_scroll = event.mp.detail.key
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    
  },
 listenerSearchInput: function (e) {
    var searchInput = e.detail.value;
    this.setData({
      searchInput: searchInput
    })
  },
 
 
  // 点击搜索
  toSearch: function (sta) {
    var that = this
    if (that.data.searchInput) {
      wx.request({
        url: 'XXXXX',
        data: {},
        success: function (res) {
          console.log('success!!!')
        },
        fail: function () {
          console.log('failed!!!')
        }
      })
    } else {
      wx.showModal({
        title: '提示',
        content: '请输入搜索内容',
        showCancel: false
      })
      return
    }
  },
 
created () {
    // let app = getApp()
  }
}
</script>

<style scoped>
div >>> .no-border {
  border-width: 0pt;
}
.top-padding {
  padding-top: 50rpx;
}
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}
.userinfo-nickname {
  color: red;
}
.usermotto {
  margin-top: 150px;
}
.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid red;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}
.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
.search{
  width: 96%;
}
.search_arr {
  border: 1px solid burlywood;
  border-radius: 20rpx;
  margin-left: 0rpx;
  height: 60rpx;
}
.search_arr input{
  margin-left: 60rpx;
  height: 60rpx;
  border-radius: 5px;
}
.bc_text {
  line-height: 68rpx;
  height: 68rpx;
  margin-top: 60rpx;
}
 
.sousuo {
  margin-left: 10rpx;
  width: 15%;
  line-height: 150%;
  text-align: center;
  border: 1px solid burlywood;
  border-radius: 10rpx;
}
.page_row{
  display: flex;
  flex-direction: row
}
.searchcion {
  margin: 15rpx 15rpx 15rpx 15rpx;
  position: absolute;
  left:5rpx;
  z-index: 2;
  width: 20px;
  height: 0px;
  text-align: center;
}
</style>