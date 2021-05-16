<template>
  <the-score :logo="logoUrl"></the-score>
</template>

<script>
import TheScore from "./components/UI/TheScore.vue";
export default {
  components: { TheScore },
  data() {
    return {
      logoUrl: require("./assets/logo.svg"),
    };
  },
};
</script>

<style>
body {
  width: 100%;
  height: 100vh;
  margin: 0 !important;
  padding: 0 !important;
  background: radial-gradient(#1f3756, #141539);
}
</style>
