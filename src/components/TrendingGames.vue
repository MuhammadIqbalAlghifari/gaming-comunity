<template>
    <section class="flex flex-col max-w-screen-2xl mx-auto md:gap-y-10 gap-y-5 justify-center items-center w-full h-auto lg:p-20 md:p-14 p-8">
        <div ref="tittle" class="flex w-full justify-between items-center">
            <h1 class="text-white lg:text-2xl md:text-xl text-lg font-semibold">Currently Trending Games</h1>
            <button class="bg-[#1c1c1c] text-white rounded-md px-4 py-2 lg:text-base md:text-sm text-xs uppercase tracking-wide">see all</button>
        </div>
        <div class="flex flex-wrap w-full lg:justify-between gap-5 lg:gap-0 justify-center items-center">
            <main v-for="(game, index) in TrendingGamesData" :key="index" ref="cards" class="flex-col flex gap-y-6 justify-center items-center">
                <img :src="game.img" class="w-full h-full object-cover rounded-lg">
                <div class="flex justify-center items-center gap-x-3">
                    <p class="text-white font-semibold lg:text-base md:text-sm text-xs">{{ game.followers }}</p>
                </div>
            </main>
        </div>
    </section>
</template>

<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

const TrendingGamesData = [
    {
        img: "/medieval-war.png",
        followers: "40 Followers"
    },
    {
        img: "/muskeeter.png",
        followers: "40 Followers"
    },
    {
        img: "/halo.png",
        followers: "40 Followers"
    },
    {
        img: "/limbo-punk.png",
        followers: "40 Followers"
    }
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