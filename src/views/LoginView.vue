<template>
  <div class="login">
    <h1>Login</h1>
    <input type="text" name="" id="">
    <input type="text" name="" id="">
    <input type="password" name="" id="">
    <button @click="fetchData">確定</button>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .login {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      data: { A: "G5CLICK" },  // 初始設置 A
    };
  },
  methods: {
    async fetchData() {
      try {
        // 使用 URLSearchParams 格式化 data 物件
        const params = new URLSearchParams(this.data);

        // 發送 POST 請求，將 params 作為資料傳遞
        const response = await axios.post('../game1.ashx', params);

        console.log(response.data); // 顯示返回的數據
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    },
  },
};
</script>