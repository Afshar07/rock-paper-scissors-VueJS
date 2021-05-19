<template>
  <div class="container">
    <div class="header">
      <h1>rules</h1>
      <svg
        class="close-icon"
        xmlns="http://www.w3.org/2000/svg"
        @click="$emit('closeRules')"
        width="20"
        height="20"
      >
        <path
          fill="#3B4262"
          fill-rule="evenodd"
          d="M16.97 0l2.122 2.121-7.425 7.425 7.425 7.425-2.121 2.12-7.425-7.424-7.425 7.425L0 16.97l7.425-7.425L0 2.121 2.121 0l7.425 7.425L16.971 0z"
          opacity=".25"
        />
      </svg>
    </div>
    <img :src="rulesImage" alt="Rules" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      rulesImage: require("../../assets/image-rules.svg"),
    };
  },
  methods: {
    focusOut() {
      this.$emit("closeRules");
    },
  },
  emits: ["closeRules"],
};
</script>
<style scoped>
.container {
  width: 20rem;
  height: 22rem;
  padding: 0 2% 2rem 2%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  background-color: #fff;
  border-radius: 10px;
}
svg {
  max-width: 304px;
  max-height: 270px;
  cursor: pointer;
}
.close-icon:hover > path {
  fill: red;
  opacity: 1;
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
