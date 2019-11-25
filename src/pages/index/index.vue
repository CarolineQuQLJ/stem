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

    <i-grid i-class="no-border">
    <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
        <i-grid-icon>
            <image :src="grid.image" />
        </i-grid-icon>
        <i-grid-label>{{grid.title}}</i-grid-label>
    </i-grid-item>
  
    </i-grid>
    <i-panel title="今日热播">
        <view style="padding: 15px;">
        <i-card  v-for="item in top" :key="item" i-class="split" :title="item.name" :extra="item.remark" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
        </i-card>

    </view>
    </i-panel>
    <i-panel :title="title_name">
    <view style="padding: 10px;">
        <i-card i-class="split" title="标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
        </i-card>
    </view>
    </i-panel>
    <i-panel title="猜你喜欢">
        <view style="padding: 10px;">
        <i-card i-class="split" title="标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
        </i-card>
    </view>
    </i-panel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title_name:"今日热播",
      grids:[
        {title:"人文",image:"/static/images/1.png"},
        {title:"军事",image:"/static/images/2.png"},
        {title:"社会",image:"/static/images/3.png"},
        {title:"自然",image:"/static/images/4.png"},
        {title:"其它",image:"/static/images/5.png"}
      ],
      top:[
        {name:"点名1",address:"地址1",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍1"},
        {name:"点名2",address:"地址2",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍2"},
        {name:"点名3",address:"地址3",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍3"},
        {name:"点名4",address:"地址4",image:"https://i.loli.net/2017/08/21/599a521472424.jpg",remark:"介绍4"}
      ],
      imgUrls: [
           '/static/images/L1.jpg',
           '/static/images/L2.jpg',
           '/static/images/L3.jpg',
           '/static/images/L4.jpg'
      ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000,
    }
  },

  methods: {
    goType(type){
      console.log(type)
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
    }
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border {
   border-width: 0pt;
}
div >>> .split {
   margin-bottom: 10pt;
}
</style>