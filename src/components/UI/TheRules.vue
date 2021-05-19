<template>
  <div class="container">
    <div class="header">
      <h1>rules</h1>
      <img :src="closeIcon" alt="Close" />
    </div>
    <img :src="rulesImage" alt="Rules">
  </div>
</template>
<script>
export default {
  data() {
    return {
      closeIcon: require("../../assets/icon-close.svg"),
      rulesImage: require("../../assets/image-rules.svg"),
    };
  },
};
</script>
<style scoped>
.container {
  width: 35vw;
  height: 60vh;
  padding: 0 1rem 2rem 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  background-color: #fff;
  border-radius: 10px;
}
h1 {
  text-transform: uppercase;
}
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
