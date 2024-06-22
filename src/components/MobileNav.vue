<template>
    <div :class="['absolute top-0 left-0 h-screen w-screen bg-[#0a0606] transform transition-transform duration-300 ease-in-out filter drop-shadow-md', open ? '-translate-y-0' : '-translate-y-full']">
      <div class="flex items-center justify-center filter drop-shadow-md bg-black h-20">
        <h1 class="text-xl text-white font-semibold">LOGO</h1>
      </div>
      <div class="flex flex-col items-center justify-center gap-y-6 py-10 text-lg text-black">
          <RouterLink class="hover:text-orange-400 text-white transition-all duration-300" to="/" @click="setOpen(false)">Home</RouterLink>
          <RouterLink class="hover:text-orange-400 text-white transition-all duration-300" to="/about" @click="setOpen(false)">About Us</RouterLink>
          <RouterLink class="hover:text-orange-400 text-white transition-all duration-300" to="/portfolio" @click="setOpen(false)">Portfolio</RouterLink>
          <RouterLink class="hover:text-orange-400 text-white transition-all duration-300" to="/news" @click="setOpen(false)">News</RouterLink>
          <RouterLink to="/contact" class="hover:text-orange-400 text-white transition-all duration-300" @click="setOpen(false)">Contact Us</RouterLink>
      </div>
    </div>
  </template>
  
  <script setup>  
  const props = defineProps({
    open: Boolean,
  });
  
  const emit = defineEmits(['set-open']);
  
  const setOpen = (val) => {
    emit('set-open', val);
  };
  </script>
  