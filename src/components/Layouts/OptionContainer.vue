<template>
  <div class="container" :style="style">
    <div class="whiteBg">
      <img :src="optionImg" alt="Choose!" />
    </div>
  </div>
</template>

<style scoped>
.container {
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.whiteBg {
  background-color: #eee;
  width: 80%;
  height: 80%;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.whiteBg:hover {
  box-shadow: 1px 1px 15px 1px #6e6e6e inset;
}
.paperStyle {
  background-image: linear-gradient(#4865f4, #5671f5);
}
.scissorStyle {
  background-image: linear-gradient(#ec9e0e, #eca922);
}
.rockStyle {
  background-image: linear-gradient(#dc2e4e, #dd405d);
}
</style>

<script>
export default {
  props: ["optionImg"],
};
</script>
