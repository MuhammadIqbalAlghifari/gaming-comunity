<template>
    <main class="lg:p-20 md:p-14 max-w-screen-2xl mx-auto p-8 flex flex-col justify-center w-full gap-y-10">
        <h1 ref="tittleOne" class="text-white lg:text-3xl md:text-xl text-base mx-auto tracking-wide text-center leading-loose max-w-3xl font-medium">Lorem Ipsum is simply dummy text of the printing and typersetting industry.</h1>
        <div ref="tittleTwo" class="flex flex-col justify-center lg:items-start items-center gap-y-4">
            <h1 class="text-white lg:text-3xl md:text-xl text-base tracking-wide text-left leading-loose font-medium">Lorem Ipsum</h1>
            <p class="text-white text-sm tracking-wide max-w-lg lg:text-left text-center leading-loose">Lorem Ipsum is simply dummy text of the printing and typersetting industry. Lorem Ipsum has been industry's standard dummy text since 1500's.</p>
        </div> 
        <img ref="image" src="/miles-morales.png" alt="" class="w-full h-auto object-cover rounded-lg">   
    </main>
</template>
<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);
const image = ref(null);
const tittleOne = ref(null)
const tittleTwo = ref(null)

const animateOnScroll = (element, { opacity, x, y }) => {
  gsap.fromTo(element, { opacity, x, y }, {
      opacity: 1,
      x: 0,
      y: 0,
      duration: 1,
      stagger: 0.3,
      delay: 0.2,
      ease: 'power3.out',
      scrollTrigger: {
        trigger: element,
        start: 'top bottom',
        end: 'center center',
      },
    }
  );
};

onMounted(() => {
  animateOnScroll(image.value, {opacity: 0, y: 50})
  animateOnScroll(tittleOne.value, {opacity: 0, y: 50})
  animateOnScroll(tittleTwo.value.children, {opacity: 0, y: 50})
});

</script>