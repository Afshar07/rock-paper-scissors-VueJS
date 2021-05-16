<template>
  <div :style="style" class="container">
    <div class="grid-container">
      <option-container
      class="paper"
        :optionImg="paperImg"
        style="background-image: linear-gradient(#4865f4, #5671f5);"
        :style="stepOneStyle"
      ></option-container>
      <option-container
      class="scissor"
        :optionImg="scissorImg"
        :style="stepOneStyle"
        style="background-image: linear-gradient(#ec9e0e, #eca922);"
      ></option-container>
      <option-container
      class="rock"
        :optionImg="rockImg"
        :style="stepOneStyle"
        style="background-image: linear-gradient(#dc2e4e, #dd405d);"
      ></option-container>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 50vw;
  height: 30rem;
  background-repeat: no-repeat;
  background-position: center center;
  display: flex;
  justify-content: center;
  align-items: center;
}
.grid-container{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  align-items: center;
  justify-items: center;
}
.paper{
  grid-column: 2/3;
}
.scissor{
  grid-column: 5/6;
}
.rock{
  grid-column:3/5;
  grid-row: 3/ -2;
}
</style>

<script>
import OptionContainer from "../Layouts/OptionContainer.vue";
export default {
  components: { OptionContainer },
  props: ["backUrl"],
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
