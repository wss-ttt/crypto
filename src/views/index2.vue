<template>
  <div class="wrapper">
    原数据：
    <br />
    <el-input v-model="d1" placeholder="请输入内容"></el-input>
    <el-button type="primary" @click="jiami" plain>加密</el-button>
    <el-button type="primary" @click="jiemi" plain>解密</el-button>
    <br />加密数据：
    <br />
    <el-input v-model="d2" placeholder="请输入内容"></el-input>
  </div>
</template>

<script>
import { Decrypt, Encrypt } from '@/utils/index.js'
export default {
  components: {},
  props: {},
  data() {
    return {
      d1: '',
      d2: ''
    }
  },
  watch: {},
  computed: {},
  methods: {
    jiami() {
      console.log('加密-----', this.d1)
      let dd = Encrypt(this.d1)
      console.log(dd)
      this.d2 = dd
      // 1 L9Pu/IxfCbYuyYVsp7RjBg==
      // 2 je3i5/PNczm6BBetLpjVAQ==
    },
    jiemi() {
      console.log('解密-----', this.d2)
      this.d1 = Decrypt(this.d2)
    }
  },
  created() {},
  mounted() {}
}
</script>
<style scoped>
</style>