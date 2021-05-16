<template>
  <div :style="style">
    
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
export default {
  props: ["backUrl"],
  computed: {
    style() {
      return "background-image:" + `url(${this.backUrl})`;
    },
  },
};
</script>
