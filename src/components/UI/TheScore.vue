<template>
  <div class="header-wrapper">
    <img :src="logo" />
    <div>Score 0</div>
  </div>
</template>

<style scoped></style>
<script>
export default {
  props: ["logo"],
};
</script>
