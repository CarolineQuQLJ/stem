<template>
  <div>
    <i-grid i-class="no-border">
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/人文历史.png" />
        </i-grid-icon>
        <i-grid-label>人文</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/军事.png" />
        </i-grid-icon>
        <i-grid-label>军事</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/社会.png" />
        </i-grid-icon>
        <i-grid-label>社会</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/探索自然.png" />
        </i-grid-icon>
        <i-grid-label>自然</i-grid-label>
    </i-grid-item>
    <i-grid-item i-class="no-border">
        <i-grid-icon>
            <image src="/static/images/其它.png" />
        </i-grid-icon>
        <i-grid-label>其它</i-grid-label>
    </i-grid-item>
    </i-grid>
    <i-panel title="今日热播">
        <view style="padding: 15px;">
        <i-card  i-class="split" title="标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
        </i-card>
        <i-card i-class="split" title="标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
        </i-card>
        <i-card i-class="split" title="标题" extra="额外内容" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
        <view slot="content">内容不错</view>
        <view slot="footer">尾部内容</view>
        </i-card>
    </view>
    </i-panel>
    <i-panel title="精品推荐">
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
      
    }
  },

  methods: {
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