<template>
    <section class="flex flex-col max-w-screen-2xl mx-auto lg:flex-row lg:pl-20 lg:justify-between justify-center gap-y-10 lg:gap-y-0 items-center w-full lg:h-screen h-full">
        <article ref="leftHero" class="flex lg:px-0 lg:py-0 px-12 pt-20 md:px-14 md:pt-24 flex-col lg:gap-y-8 gap-y-4 justify-center lg:items-start items-center">
            <div class="flex justify-center items-center gap-x-2">
                <a href="/" class="text-white text-xs">Home</a>
                <p class="text-white text-sm">></p>
                <a href="#" class="text-orange-600 text-sm">About us</a>
            </div>
            <h1 class="lg:text-4xl md:text-2xl text-xl text-center lg:text-start text-white font-bold max-w-lg lg:leading-normal leading-normal">Lorem Ipsum is simply dummy text of the printing and.</h1>
            <p class="text-white lg:text-sm text-xs text-center lg:text-start max-w-sm lg:leading-loose leading-loose">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since 1500s.</p>
            <button class="text-white bg-orange-500 rounded-full lg:text-base text-sm lg:px-8 lg:py-4 px-6 py-2">Get in touch</button>
        </article>
        <img ref="rightHero" src="/limbo-punk-about.png" alt="" class="h-full max-w-xl w-full lg:py-20 object-cover">
    </section>
</template>

<script setup>

import { ref, onMounted } from 'vue';
import gsap from 'gsap';

const leftHero = ref(null)
const rightHero = ref(null)

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

const animateOnDekstop = () => {
    animateOnScroll(leftHero.value.children, {opacity: 0})
    animateOnScroll(rightHero.value, {opacity: 0, x: 1000},)
}

const animateOnMobile = () => {
    animateOnScroll(leftHero.value.children, {opacity: 0, y: -10})
    animateOnScroll(rightHero.value, {opacity: 0, y: 100})
}


onMounted(() => {
    const isDekstop = window.matchMedia("(min-width: 1028px)").matches
    isDekstop ? animateOnDekstop() : animateOnMobile()
});


</script>