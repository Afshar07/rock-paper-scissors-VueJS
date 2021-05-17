<template>
  <div :style="style" class="container">
    <div class="grid-container">
      <option-container
        class="paper paperStyle"
        @click="$emit('paper')"
        :optionImg="paperImg"
        :style="stepOneStyle"
      ></option-container>
      <option-container
        class="scissor scissorStyle"
        @click="$emit('scissor')"
        :optionImg="scissorImg"
        :style="stepOneStyle"
      ></option-container>
      <option-container
        class="rock rockStyle"
        @click="$emit('rock')"
        :optionImg="rockImg"
        :style="stepOneStyle"
      ></option-container>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 65vw;
  height: 30rem;
  background-repeat: no-repeat;
  background-position: center center;
  display: flex;
  justify-content: center;
  align-items: center;
}
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  align-items: center;
  justify-items: center;
}
.paper {
  grid-column: 2/3;
}
.scissor {
  grid-column: 5/6;
}
.rock {
  grid-column: 3/5;
  grid-row: 3/ -2;
}
</style>

<script>
import OptionContainer from "../Layouts/OptionContainer.vue";
export default {
  components: { OptionContainer },
  props: ["backUrl"],
  emits: ["paper", "scissor", "rock"],
  computed: {
    style() {
      return "background-image:" + `url(${this.backUrl})`;
    },
  },
  data() {
    return {
      rockImg: require("../../assets/icon-rock.svg"),
      paperImg: require("../../assets/icon-paper.svg"),
      scissorImg: require("../../assets/icon-scissors.svg"),
      stepOneStyle: "width: 8rem; height: 8rem",
    };
  },
};
</script>
