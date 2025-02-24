<script setup>
    const props =  defineProps(['alt','className','src','width','height']);

</script>
<template>
    <img :class="props.className" :src="props.src" :alt="props.alt" :width="props.width" :height="props.height"/>
</template>
<style>

</style>