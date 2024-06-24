<template>
    <section class="flex lg:p-20 md:p-14 p-8 max-w-screen-2xl mx-auto flex-col justify-center items-center w-full lg:pt-40 md:pt-32 pt-24">
        <article ref="topHero" class="flex flex-col lg:gap-y-8 gap-y-4 justify-center items-center">
            <div class="flex justify-center items-center gap-x-2">
                <a href="/" class="text-white text-xs">Home</a>
                <p class="text-white text-sm">></p>
                <a href="#" class="text-orange-600 lg:text-sm text-xs">Portfolio</a>
            </div>
            <h1 class="lg:text-4xl md:text-2xl text-xl text-white font-bold text-center leading-normal">Lorem Ipsum is simply dummy text of the printing and</h1>
            <p class="text-white text-center lg:text-start lg:text-sm text-xs leading-loose lg:leading-loose">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
            <div class="flex flex-wrap lg:flex-nowrap justify-between w-full bg-[#1c1c1c] lg:px-16 lg:py-10 md:px-14 md:py-8 px-10 py-4 rounded-lg">
                <div class="flex flex-col md:flex-row justify-center items-center md:gap-x-5 gap-y-5 lg:gap-x-10">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="lg:w-10 lg:h-10 w-8 h-8 rounded-full text-black bg-white p-1.5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 6a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0ZM4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.933 17.933 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632Z" />
                    </svg>
                    <div class="flex-col flex justify-center md:items-start items-center gap-y-2">
                        <h1 class="font-bold lg:text-base text-sm text-white">90+</h1>
                        <p class="text-white lg:text-base text-xs">Clients</p>
                    </div>
                </div>
                <hr class="w-1 bg-white h-auto hidden md:block"/>
                <div class="flex flex-col md:flex-row justify-center items-center md:gap-x-5 gap-y-5 lg:gap-x-10">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="lg:w-10 lg:h-10 w-8 h-8 rounded-full text-black bg-white p-1.5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z" />
                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1 1 15 0Z" />
                    </svg>
                    <div class="flex-col flex justify-center md:items-start items-center gap-y-2">
                        <h1 class="font-bold lg:text-base text-sm text-white">30+</h1>
                        <p class="text-white lg:text-base text-xs">Countries</p>
                    </div>
                </div>
                <hr class="w-1 bg-white h-auto hidden md:block"/>
                <div class="flex flex-col md:flex-row justify-center items-center md:gap-x-5 gap-y-5 lg:gap-x-10">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="lg:w-10 lg:h-10 w-8 h-8 rounded-full text-black bg-white p-1.5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M5.25 14.25h13.5m-13.5 0a3 3 0 0 1-3-3m3 3a3 3 0 1 0 0 6h13.5a3 3 0 1 0 0-6m-16.5-3a3 3 0 0 1 3-3h13.5a3 3 0 0 1 3 3m-19.5 0a4.5 4.5 0 0 1 .9-2.7L5.737 5.1a3.375 3.375 0 0 1 2.7-1.35h7.126c1.062 0 2.062.5 2.7 1.35l2.587 3.45a4.5 4.5 0 0 1 .9 2.7m0 0a3 3 0 0 1-3 3m0 3h.008v.008h-.008v-.008Zm0-6h.008v.008h-.008v-.008Zm-3 6h.008v.008h-.008v-.008Zm0-6h.008v.008h-.008v-.008Z" />
                    </svg>
                    <div class="flex-col flex justify-center md:items-start items-center gap-y-2">
                        <h1 class="font-bold lg:text-base text-sm text-white">50+</h1>
                        <p class="text-white lg:text-base text-xs">Projects</p>
                    </div>
                </div>
            </div>
        </article>
    </section>
</template>

<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';

const topHero = ref(null)

const animateOnScroll = (element, {opacity, x, y}) => {
    gsap.fromTo(element, {opacity, x, y}, {
        opacity: 1,
        x: 0,
        y: 0,
        duration: 1,
        stagger: 0.3,
        delay: 0.1,
        ease: 'power3.out',
    }) 
}



onMounted(() => {
    animateOnScroll(topHero.value.children, {opacity: 0, y: 25})
});

</script>