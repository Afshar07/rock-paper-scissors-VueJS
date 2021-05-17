<template>
  <keep-alive>
    <the-score :logo="logoUrl" :score="score"></the-score>
  </keep-alive>
  <step-one
    @paper="playerHasChoosenPaper()"
    @scissor="playerHasChoosenScissor()"
    @rock="playerHasChoosenRock()"
    v-if="currentStep === 'step-one'"
    :backUrl="backgroundImg"
  ></step-one>
  <step-two
    v-else-if="currentStep === 'step-two'"
    :choosen="stepTwoClass"
    :choosenImg="choosenImg"
    @rendered="onRenderChild($event)"
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
      pcChoosen: "",
      playerChoosen: "",
      winner: "",
    };
  },
  watch: {
    pcChoosen() {
      this.determineWinner();
    },
    winner(value) {
      if (value == "player") {
        this.score++;
      } else if (value == "draw") {
        return;
      } else {
        this.score--;
      }
    },
  },

  methods: {
    determineWinner() {
      const winningMap = { rock: "scissor", paper: "rock", scissor: "paper" };
      if (this.pcChoosen == this.playerChoosen) {
        this.winner = "draw";
      } else if (this.pcChoosen === winningMap[this.playerChoosen]) {
        this.winner = "player";
      } else {
        this.winner = "computer";
      }
      console.log(winningMap[this.playerChoosen]);
      return;
    },
    playerHasChoosenPaper() {
      this.currentStep = "step-two";
      this.stepTwoClass = "paperStyle";
      this.choosenImg = require("./assets/icon-paper.svg");
      this.playerChoosen = "paper";
    },
    playerHasChoosenScissor() {
      this.currentStep = "step-two";
      this.stepTwoClass = "scissorStyle";
      this.choosenImg = require("./assets/icon-scissors.svg");
      this.playerChoosen = "scissor";
    },
    playerHasChoosenRock() {
      this.currentStep = "step-two";
      this.stepTwoClass = "rockStyle";
      this.choosenImg = require("./assets/icon-rock.svg");
      this.playerChoosen = "rock";
    },
    onRenderChild(value) {
      this.pcChoosen = value;
      console.log(this.pcChoosen);
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
