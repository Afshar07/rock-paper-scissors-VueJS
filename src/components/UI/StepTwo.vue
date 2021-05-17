<template>
  <div class="container">
    <div class="playerChoice">
      <p>You picked</p>
      <option-container
        :style="stepTwoStyle"
        :class="choosen"
        :optionImg="choosenImg"
      ></option-container>
    </div>
    <div class="computerChoice">
      <p>The House Picked</p>
      <div class="beforePcChoose" v-if="show"></div>
      <option-container
        :style="stepTwoStyle"
        :optionImg="pcChoosenImg"
        :class="pcChoosenClass"
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
export default {
  props: ["choosen", "choosenImg"],
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
    renderPcChoose() {
      this.pcChoose();
      console.log(this.pcChoosen);
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
    },
  },
  components: { OptionContainer },
  mounted() {
    setTimeout(() => {
      this.show = false;
      this.renderPcChoose();
    }, 3000);
  },
};
</script>
