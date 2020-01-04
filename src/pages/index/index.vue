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
        <i-card  v-for="item in top" :key="item" i-class="split" :title="item.name" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
        </i-card>

    </view>
    </i-panel>
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
        {name:"《Oceans海洋》",address:"BBC <法>雅克·贝汉、雅克·克鲁佐德",image:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575453637872&di=e4763ddf1e9cb1c6c66818e058aae7ff&imgtype=0&src=http%3A%2F%2Fhbimg.b0.upaiyun.com%2F984baf97133e96eaed010374131571407d0240552887c-LREQgK_fw658",remark:"深入探索这个幽深而富饶的神秘世界、完整地呈现海洋的壮美辽阔。"},
        {name:"《风味人间》",address:"陈晓卿",image:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575453905608&di=e071ae67ad543636a705711fe9413acb&imgtype=jpg&src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fq_70%2Cc_zoom%2Cw_640%2Fimages%2F20190416%2F0f7d2db6dd79440fa64d4d2c868697f3.jpeg",remark:"世界美食背后，有着浓浓的人情味，食物的迁徙背后，正有着移民迁徙的足印。"},
        {name:"《Free Solo徒手攀岩》",address:"<美>金国威、伊丽莎白·柴·瓦萨赫伊",image:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1575453993670&di=bb455c573cbc2d1ce6576794d94c2bbb&imgtype=0&src=http%3A%2F%2Fimage.thepaper.cn%2Fwww%2Fimage%2F15%2F966%2F526.jpg",remark:"美国攀岩大师亚历克斯·霍诺德（Alex Honnold）2017年6月3日无辅助徒手攻克美国约塞米蒂国家公园3000英尺高的酋长岩的全过程，共用时3小时56分钟。"},
   
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