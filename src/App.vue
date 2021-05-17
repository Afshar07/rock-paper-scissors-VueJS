<template>
  <keep-alive>
    <the-score :logo="logoUrl" :score="score"></the-score>
  </keep-alive>
  <step-one
    @paper="playerHasChoosenPaper()"
    v-if="currentStep === 'step-one'"
    :backUrl="backgroundImg"
  ></step-one>
  <step-two
    v-else-if="currentStep === 'step-two'"
    :choosen="stepTwoClass"
    :choosenImg="choosenImg"
  ></step-two>
</template>

<script>
import TheScore from "./components/UI/TheScore.vue";
import StepOne from "./components/UI/StepOne.vue";
import StepTwo from "./components/UI/StepTwo.vue";
export default {
  components: { TheScore, StepOne, StepTwo },
  data() {
    return {
      currentStep: "step-one",
      stepTwoClass: "",
      logoUrl: require("./assets/logo.svg"),
      score: "0",
      backgroundImg: require("./assets/bg-triangle.svg"),
      choosenImg: "",
    };
  },
  methods: {
    playerHasChoosenPaper() {
      this.currentStep = "step-two";
      this.stepTwoClass = "paperStyle";
      this.choosenImg = require("./assets/icon-paper.svg");
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Barlow+Semi+Condensed:wght@600;700&display=swap");
body {
  width: 100%;
  height: 100vh;
  margin: 0 !important;
  padding: 0 !important;
  font-family: "Barlow Semi Condensed", sans-serif;
  background: radial-gradient(#1f3756, #141539);
  display: flex;
  justify-content: center;
}
</style>
