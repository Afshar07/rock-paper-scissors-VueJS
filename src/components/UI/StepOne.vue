<template>
  <div :style="style">
    <option-container
      :optionImg="paperImg"
      style="background-image: linear-gradient(#4865f4, #5671f5);"
      :style="stepOneStyle"
    ></option-container>
    <option-container
      :optionImg="scissorImg"
      :style="stepOneStyle"
      style="background-image: linear-gradient(#ec9e0e, #eca922);"
    ></option-container>
    <option-container
      :optionImg="rockImg"
      :style="stepOneStyle"
      style="background-image: linear-gradient(#dc2e4e, #dd405d);"
    ></option-container>
  </div>
</template>

<style scoped>
div {
  width: 50vw;
  height: 30rem;
  background-repeat: no-repeat;
  background-position: center center;
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
