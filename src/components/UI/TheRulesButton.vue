<template>
  <button @click="$emit('openRules')">rules</button>
</template>

<script>
export default {
    emits: ["openRules"]
};
</script>
<style scoped>
button {
  width: 10vw;
  height: 6vh;
  border-radius: 6px;
  font-weight: 700;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: 1px;
  background: transparent;
  border: 1px solid #fff;
  cursor: pointer;
}
</style>
