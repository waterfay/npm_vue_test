<script setup>
    import {ref} from 'vue';
    const msg = ref("<strong>你好</strong>，歡迎來到<span style='color:blue;'>Vue 3</span>");
</script>
<template>
<p v-html="msg"></p>
</template>