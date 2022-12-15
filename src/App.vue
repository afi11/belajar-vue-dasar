<template>
  <DeklaratifRendering />
</template>

<script>
import DeklaratifRendering from "./components/DeklaratifRendering.vue";

export default {
  name: 'App',
  components: {
    DeklaratifRendering
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
