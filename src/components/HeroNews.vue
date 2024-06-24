<template>
    <section class="flex lg:p-20 p-8 md:p-14 max-w-screen-2xl mx-auto flex-col justify-center items-center w-full lg:pt-40 md:pt-32 pt-24">
        <article ref="topHero" class="flex flex-col lg:gap-y-8 gap-y-4 justify-center items-center">
            <div class="flex justify-center items-center gap-x-2">
                <a href="/" class="text-white text-xs">Home</a>
                <p class="text-white text-sm">></p>
                <a href="#" class="text-orange-600 text-sm">News</a>
            </div>
            <h1 class="lg:text-4xl md:text-2xl text-xl text-white font-bold text-center leading-normal">Lorem Ipsum is simply dummy text of the printing and</h1>
            <p class="text-white lg:text-sm text-xs text-center lg:text-start leading-loose">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
            <div class="flex justify-around items-center w-auto gap-x-5 bg-[#1c1c1c] rounded-full lg:py-2 lg:px-6 px-4 py-2">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="white" class="lg:w-7 lg:h-7 w-5 h-5 text-white">
                    <path stroke-linecap="round" stroke-linejoin="round" d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z" />
                </svg>
                <input type="text" placeholder="Search" class="text-white bg-transparent lg:text-base text-xs focus:outline-none outline-none">
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