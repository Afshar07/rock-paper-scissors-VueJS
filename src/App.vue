<template>
  <the-score :logo="logoUrl" :score="score"></the-score>
  <the-wrapper :backUrl="backgroundImg"></the-wrapper>
</template>

<script>
import TheScore from "./components/UI/TheScore.vue";
import TheWrapper from "./components/UI/TheWrapper.vue";
export default {
  components: { TheScore, TheWrapper },
  data() {
    return {
      logoUrl: require("./assets/logo.svg"),
      score: "0",
      backgroundImg: require("./assets/bg-triangle.svg"),
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Barlow+Semi+Condensed:wght@600;700&display=swap");
body {
  width: 100vw;
  height: 100vh;
  margin: 0 !important;
  padding: 0 !important;
  font-family: "Barlow Semi Condensed", sans-serif;
  background: radial-gradient(#1f3756, #141539);
  display: flex;
  justify-content: center;
}
</style>
