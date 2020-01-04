  <template>
  <div>
    <i-panel title="  ">
      <view>
        <i-card i-class="split" v-for="item in recommand" :key="item" :extra="item.name" :thumb="item.img">
            <view slot="content">推荐：{{item.remark}}</view>
            <view slot="footer">地址：{{item.introduction}}</view>
        </i-card>
      </view>
    </i-panel>
  </div>
</template>

<script>

export default{
  data () {
    return {
      list:[]
    }
  },
 
  onLoad (option){
    console.log(option.type)
    this.list = require('@/data/' + option.type + '.json')
  },

  methods: {
  },
  created () {
  }
}
</script>

<style scoped>
div >>> .split {
   margin-bottom: 10pt;
}
</style>