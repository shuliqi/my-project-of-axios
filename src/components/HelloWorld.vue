<template>
  <div class="hello">
    <button @click="onClick">请求</button>
  </div>
</template>

<script>
import VeryAxios from 'very-axios'
const request = new VeryAxios({
  cancelDuplicated: true,
  duplicatedKeyFn: (config) => {
    const { method, url, responseType } = config
    return `${method}${url}${responseType}`
  },
  tipFn: (err) => console.log('err', err)
})
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    onClick () {
      request.GET('https://www.fastmock.site/mock/d867c364f89208a7672e9e9d0a822417/qixiao/manageTrend')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
