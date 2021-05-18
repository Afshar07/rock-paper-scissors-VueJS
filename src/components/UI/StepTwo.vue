<template>
  <div class="container">
    <div class="playerChoice">
      <p>You picked</p>
      <!-- Show Player Choice -->
      <option-container
        :style="stepTwoStyle"
        :class="choosen"
        bigger="bigger"
        :optionImg="choosenImg"
      ></option-container>
    </div>
    <!-- Result and play again button when bot choice is rendered -->
    <play-again v-if="pcChoosen" :winner="winnerState" @playagain="$emit('play-again')"> </play-again>
    <div class="computerChoice">
      <p>The House Picked</p>
      <!-- Empy circle before bot chooses -->
      <div class="beforePcChoose" v-if="show"></div>
      <!-- Bot Choice -->
      <option-container
        :style="stepTwoStyle"
        :optionImg="pcChoosenImg"
        :class="pcChoosenClass"
        bigger="bigger"
        v-else
      ></option-container>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 65vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
.playerChoice {
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.computerChoice {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 50%;
}
.playerChoice p,
.computerChoice p {
  text-transform: uppercase;
  letter-spacing: 2px;
  color: #fff;
  font-size: 1.3rem;
  text-align: start;
}
.beforePcChoose {
  width: 14rem;
  height: 14rem;
  border-radius: 50%;
  background-color: #141539;
}
</style>

<script>
import OptionContainer from "../Layouts/OptionContainer.vue";
import PlayAgain from "../Layouts/PlayAgain.vue";
export default {
  components: { OptionContainer, PlayAgain },
  props: ["choosen", "choosenImg", "winnerState"],
  emits: ["rendered", "play-again"],
  data() {
    return {
      stepTwoStyle: "width: 14rem; height: 14rem",
      styleTwo: "background-color: black;",
      show: true,
      pcChoosen: "",
      pcChoosenImg: "",
      pcChoosenClass: "",
    };
  },
  methods: {
    // House (bot) Choice
    pcChoose() {
      const randNumber = Math.floor(Math.random() * 3 + 1);
      if (randNumber === 1) {
        this.pcChoosen = "scissor";
      } else if (randNumber === 2) {
        this.pcChoosen = "paper";
      } else if (randNumber === 3) {
        this.pcChoosen = "rock";
      }
    },
    // Show House (bot) choice
    renderPcChoose() {
      // Call the method for bot choice
      this.pcChoose();
      // Render image for bot choice
      if (this.pcChoosen == "rock") {
        this.pcChoosenImg = require("../../assets/icon-rock.svg");
        this.pcChoosenClass = "rockStyle";
      } else if (this.pcChoosen == "paper") {
        this.pcChoosenImg = require("../../assets/icon-paper.svg");
        this.pcChoosenClass = "paperStyle";
      } else if (this.pcChoosen == "scissor") {
        this.pcChoosenImg = require("../../assets/icon-scissors.svg");
        this.pcChoosenClass = "scissorStyle";
      }
      // Send bot choice to app.vue
      this.$emit("rendered", this.pcChoosen);
    },
  },
  mounted() {
    setTimeout(() => {
      this.show = false;
      this.renderPcChoose();
    }, 200);
  },
};
</script>
