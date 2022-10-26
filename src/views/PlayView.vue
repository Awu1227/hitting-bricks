<template>
  <div class="play">
    <div id="playground">
      <span id="ball"></span>
    </div>
  </div>
</template>
<script setup>
import { onMounted } from 'vue';
onMounted(() => {
  console.log(1);
});
</script>
<style scoped>
@media (min-width: 1024px) {
  .play {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
#playground {
  width: 80vw;
  height: 80vh;
  border: solid 2px red;
  border-radius: 8px;
  position: relative;
}
#ball {
  width: 20px;
  height: 20px;
  background-color: red;
  position: absolute;
  border-radius: 10px;
  left: 0;
}
</style>
