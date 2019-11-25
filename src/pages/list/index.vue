<template>
  <div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      
    }
  },
 
  onLoad (option){
    console.log(option.type)
    //this.recommand = require('@/data/' + option.type + '.json')
  },

  methods: {
  },

  created () {
  }
}
</script>

<style scoped>
</style>