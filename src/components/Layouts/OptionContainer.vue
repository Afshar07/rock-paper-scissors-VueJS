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
</style>

<script>
export default {
  props: ["optionImg"],
};
</script>
