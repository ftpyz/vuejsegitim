<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Oyun />
  </div>
</template>

<script>
import Oyun from "./components/Oyun.vue";

export default {
  name: "app",
  components: {
    Oyun
  }
};
</script>
