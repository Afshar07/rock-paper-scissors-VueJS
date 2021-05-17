<template>
  <div class="header-wrapper">
    <img :src="logo" />
    <div class="scoreContainer">
      <p>score</p>
      <p class="score">{{ score }}</p>
    </div>
  </div>
</template>

<style scoped>

.header-wrapper {
  width: 100% ;
  display: flex;
  justify-content: space-between;
  border: 2px solid #606e85;
  padding: 1rem;
  margin-top: 1rem;
  border-radius: 10px;
}
.scoreContainer {
  width: 25%;
  height: 80%;
  background-color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 10px;
}
.scoreContainer p {
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #2a46c0;
}
.score{
  font-size: 2.3rem;
  margin: 0 0 1rem 0;
  color: #3b4363 !important;
}
</style>
<script>
export default {
  props: ["logo", "score"],
};
</script>
