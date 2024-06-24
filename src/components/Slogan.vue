<template>
    <section class="flex flex-col max-w-screen-2xl mx-auto justify-center items-center gap-y-10 w-full h-full lg:p-20 md:p-14 p-8">
        <h1 ref="tittle" class="lg:text-2xl md:text-xl text-lg text-white text-center font-semibold"> Why work with us?</h1>
        <div class="flex flex-col lg:flex-row justify-center h-full gap-y-10 lg:gap-10 items-center w-full">
            <main v-for="(data, index) in whyData" :key="index" ref="cards" class="bg-[#1c1c1c] flex flex-col justify-center items-center w-full md:px-10 md:py-16 p-5 rounded-lg gap-y-5">
                <h1 class="lg:text-xl md:text-lg text-base text-white text-center">{{ data.tittleTwo }}</h1>
                <h1 class="md:text-sm text-sm text-white text-center">{{ data.description }}</h1>
                <p class="md:text-sm text-sm text-white bg-green-600 px-6 py-3 rounded-lg">{{ data.tittle }}</p>
            </main>
        </div>
    </section>
</template>

<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

const whyData = [
    {
        tittle: "Lorem Ipsum",
        tittleTwo: "Lorem Ipsum",
        description: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500's",
    },
    {
        tittle: "Lorem Ipsum",
        tittleTwo: "Lorem Ipsum",
        description: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500's",
    },
    {
        tittle: "Lorem Ipsum",
        tittleTwo: "Lorem Ipsum",
        description: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500's",
    },
];

const cards = ref([]);
const tittle = ref(null)

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
  cards.value.forEach(card => {
    animateOnScroll(card, { opacity: 0, y: 50 });
  });
  animateOnScroll(tittle.value, {opacity: 0})
});

</script>