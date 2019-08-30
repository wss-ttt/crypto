<template>
  <div class="wrapper">
      <button @click="test">加密</button>
  </div>
</template>

<script>
import CryptoJS from 'crypto-js'
export default {
  components: {},
  props: {},
  data() {
    return {}
  },
  watch: {},
  computed: {},
  methods: {
    test() {
        // 加密处理 
        var password = 'admin'
        var text = CryptoJS.AES.encrypt(password, 'secret key 123').toString();//使用CryptoJS方法加密
        console.log(text)
        // 解密处理 
        var bytes = CryptoJS.AES.decrypt(text,'secret key 123').toString(CryptoJS.enc.Utf8)
        console.log(bytes)
    }
  },
  created() {},
  mounted() {}
}
</script>
<style scoped>
</style>