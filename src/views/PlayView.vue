<template>
  <div class="play">
    <div id="playground">
      <span id="ball" ref="ball"></span>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';
const ball = ref(null);
onMounted(() => {
  let speedX = parseInt(Math.random() * 4) + 3;
  let speedY = parseInt(Math.random() * 5) + 3;
  const oball = ball.value;
  const tick = () => {
    oball.style.left = oball.offsetLeft + speedX + 'px';
    oball.style.top = oball.offsetTop + speedY + 'px';
    if (oball.offsetLeft >= 980 || oball.offsetLeft <= 0) {
      speedX *= -1;
    }
    if (oball.offsetTop >= 480 || oball.offsetTop <= 0) {
      speedY *= -1;
    }
    requestAnimationFrame(tick);
  };
  tick();
});
</script>
<style scoped>
@media (min-width: 1024px) {
  .play {
    min-height: 90vh;
    display: flex;
    align-items: center;
  }
}
#playground {
  width: 1000px;
  height: 500px;
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
