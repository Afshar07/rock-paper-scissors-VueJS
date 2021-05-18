<template>
  <div class="container">
    <h2>{{ winner }}</h2>
    <button class="play-again" @click="$emit('playagain')">Play Again</button>
  </div>
</template>
<style scoped></style>

<script>
export default {
  props: ["winner"],
  emits: ["playagain"],
};
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
h2 {
  color: #fff;
  font-size: 2rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.play-again {
  font-family: "Barlow Semi Condensed", sans-serif;
  font-size: 1.2rem;
  background-color: #fff;
  color: #3b4363;
  letter-spacing: 2px;
  text-transform: uppercase;
  border: none;
  width: 45%;
  height: 7vh;
  border-radius: 10px;
  cursor: pointer;
}
.play-again:hover {
  color: #cc0000;
}
</style>
