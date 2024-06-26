<template>
    <header ref="navbarRef" class="fixed z-50 w-full">
      <nav class="flex md:px-14 md:py-7 p-5 justify-between items-center w-full bg-[#050301] text-white">
        <MobileNav :open="open" @set-open="setOpen" />
        <h1 class="lg:text-2xl md:text-xl text-lg font-bold cursor-pointer">LOGO</h1>
        <ul class="md:flex hidden items-center justify-between w-[45%] xl:text-sm text-xs">
          <RouterLink class="hover:text-orange-400 transition-all duration-300" to="/">Home</RouterLink>
          <RouterLink class="hover:text-orange-400 transition-all duration-300" to="/about">About Us</RouterLink>
          <RouterLink class="hover:text-orange-400 transition-all duration-300" to="/portfolio">Portfolio</RouterLink>
          <RouterLink class="hover:text-orange-400 transition-all duration-300" to="/news">News</RouterLink>
          <RouterLink to="/contact" class="hover:text-orange-400 transition-all duration-300">Contact Us</RouterLink>
        </ul>
        <div class="flex relative w-8 h-8 flex-col justify-between items-center md:hidden" @click="toggleOpen">
          <span :class="['h-1 w-full rounded-lg transform transition duration-300 ease-in-out', open ? 'rotate-45 translate-y-3.5 bg-white' : 'bg-white']"></span>
          <span :class="['h-1 w-full rounded-lg transform transition-all duration-300 ease-in-out', open ? 'w-0 h-0' : 'bg-white w-full']"></span>
          <span :class="['h-1 w-full rounded-lg transform transition duration-300 ease-in-out', open ? '-rotate-45 -translate-y-3.5 bg-white' : 'bg-white']"></span>
        </div>
      </nav>
    </header>
  </template>
  
  <script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  import gsap from 'gsap';
  import MobileNav from './MobileNav.vue'; 
  
  const open = ref(false);
  const isScrolled = ref(false);
  const navbarRef = ref(null);
  
  const setOpen = (val) => {
    open.value = val;
  };
  
  const toggleOpen = () => {
    open.value = !open.value;
  };
  
  onMounted(() => {
    gsap.fromTo(navbarRef.value, { opacity: 0, y: -100 }, { opacity: 1, y: 0, duration: 1.5 });
  });
  
  onBeforeUnmount(() => {
  });
  </script>

  <style>
    .router-link-active {
      color: orange;
    }
  </style>
  