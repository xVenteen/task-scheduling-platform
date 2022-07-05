<script setup>
import Layout from './view/index.vue'
</script>

<template>
  <Layout></Layout>
</template>

<style lange="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

body {
  margin: 0;
  padding: 0;
  overflow-x: hidden
}

/* 全局使用怪异和模型 */
/* :root {
  box-sizing: border-box
}

*,
::before::after {
  box-sizing: inherit;
} */

div {
  /* border: 1px solid; */
  margin: 0;
  padding: 0;
}
</style>
