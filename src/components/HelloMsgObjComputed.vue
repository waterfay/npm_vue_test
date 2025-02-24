<script setup>
import { reactive, ref, watch } from 'vue';

// ✅ 定義 isChanged
const isChanged = ref(false);

// ✅ 定義 msg 變數
const msg = reactive({
  id: 'container',
  class: 'wrapper',
  style: 'background-color: green; color: white; padding: 10px;',
});

// ✅ 監聽 isChanged，當它變更時自動修改 msg.style
watch(isChanged, (newVal) => {
  msg.style = newVal
    ? 'background-color: blue; color: yellow; padding: 20px;'
    : 'background-color: green; color: white; padding: 10px;';
});

// ✅ 點擊後變色，3 秒後自動恢復
const changeStyle = () => {
  isChanged.value = true;
  setTimeout(() => {
    isChanged.value = false;
  }, 3000);
};
</script>

<template>
  <p v-bind="msg">動態綁定段落</p>
  <button @click="changeStyle">改變樣式</button>
</template>