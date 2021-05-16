<template>
  <div class="container" :style="style">
    <div class="whiteBg">
      <img :src="optionImg" alt="Choose!" />
    </div>
  </div>
</template>

<style scoped>
    .container{
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
    }
    .whiteBg{
        background-color: #eee;
        width: 80%;
        height: 80%;
        border-radius: 50%;
                display: flex;
        justify-content: center;
        align-items: center;
    }
</style>


<script>
export default {
  props: ["optionImg"],
};
</script>
