<script setup>
import { RouterView } from 'vue-router';
import Navbar from './components/Navbar.vue';
import Lenis from 'lenis'
import { onMounted } from 'vue';
onMounted(() => {
  const lenis = new Lenis()

  function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
  }

  requestAnimationFrame(raf)
});
</script>

<template>
  <Navbar/>
    <div>
      <RouterView/>
    </div>
</template>

