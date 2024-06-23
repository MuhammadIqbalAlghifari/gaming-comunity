<script setup>
import { RouterView } from 'vue-router';
import Loader from './components/Loader.vue'
import Navbar from './components/Navbar.vue';
</script>

<template>
  <Navbar/>
  <Suspense>
    <template #default>
      <div>
        <RouterView/>
      </div>
    </template>
    <template #fallback><Loader/></template>
  </Suspense>
</template>

