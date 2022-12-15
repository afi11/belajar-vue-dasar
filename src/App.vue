<template>
  <DeklaratifRendering />
  <!-- Ganti Materi -->
  <EventListener />
  <!-- Ganti Materi -->
  <TwoWayDataBinding />
  <!-- Ganti Materi -->
  <ConditionalVue />
</template>

<script>
import DeklaratifRendering from "./components/DeklaratifRendering.vue";
import EventListener from "./components/EventListener.vue";
import TwoWayDataBinding from "./components/TwoWayDataBinding.vue";
import ConditionalVue from "./components/Conditional.vue";

export default {
  name: 'App',
  components: {
    DeklaratifRendering,
    EventListener,
    TwoWayDataBinding,
    ConditionalVue
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
