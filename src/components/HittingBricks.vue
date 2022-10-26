<script setup>
import { RouterLink } from 'vue-router';
import { ref } from 'vue';

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <h1>{{ msg }}</h1>
  <RouterLink to="/play" class="btn btn--white .btn--animated"
    >play now</RouterLink
  >
</template>

<style scoped>
.btn {
  color: red;
}
.btn:link,
.btn:visited {
  text-transform: uppercase;
  text-decoration: none;
  padding: 1.5rem 4rem;
  display: inline-block;
  border-radius: 10rem;
  transition: all 0.2s;
  position: relative;
  font-size: 1.6rem;
}

.btn:hover {
  transform: translateY(-0.3rem);
  box-shadow: 0 10rem 20rem rgba(0, 0, 0, 0.2);
}
.btn:hover::after {
  transform: scaleX(1.4) scaleY(1.6);
  opacity: 0;
}

.btn:active {
  transform: translateY(-0.1rem);
  box-shadow: 0 5rem 10rem rgba(0, 0, 0, 0.2);
}

.btn--white {
  background-color: white;
  color: #777;
}
.btn--white::after {
  background-color: white;
  color: #777;
}

.btn::after {
  content: '';
  display: inline-block;
  height: 100%;
  width: 100%;
  border-radius: 10rem;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  transition: all 0.4s;
}

.btn--animated {
  animation: moveInBottm 0.5s ease-out 0.75s;
  animation-fill-mode: backwards;
}
</style>
