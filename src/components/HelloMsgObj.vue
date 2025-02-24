<script setup>
import { reactive, ref } from 'vue';
const msg = reactive({
    id: 'container',
    class: 'wrapper',
    style: 'background-color: green; color: white; padding: 10px;',
});

const originalStyle = msg.style;

const changeStyle = () =>{
    msg.style = 'background-color: blue; color: yellow; padding: 20px;';
    setTimeout(() =>{
        msg.style = originalStyle;
    },3000);
}
</script>
<template>
    <p :="msg">動態綁定段落</p>
    <button @click="changeStyle">改變樣式</button>
</template>