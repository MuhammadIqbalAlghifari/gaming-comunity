<template>
    <section class="lg:p-20 p-8 md:p-14 max-w-screen-2xl mx-auto flex flex-wrap-reverse lg:flex-nowrap w-full lg:justify-between justify-center gap-y-5 lg:gap-y-0 items-center">
        <article ref="leftHero" class="flex-col flex justify-center lg:items-start items-center lg:gap-y-10 gap-y-5">
            <h1 class="font-semibold lg:text-4xl md:text-2xl text-xl leading-relaxed text-center lg:text-start lg:leading-relaxed text-white lg:max-w-xl">Lorem Ipsum is simply dummy text dummy text</h1>
            <p class="leading-relaxed lg:leading-relaxed text-white lg:max-w-md text-center lg:text-start md:text-sm text-xs font-extralight">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. it has survived not only five centuries.</p>
            <p class="leading-relaxed lg:leading-relaxed text-white lg:max-w-md text-center lg:text-start md:text-sm text-xs font-extralight">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
            <button class="bg-orange-500 md:px-6 md:py-3 px-4 py-2 text-xs md:text-base rounded-full text-white">Read More</button>
        </article>
        <img ref="rightHero" src="/limbo-punk-about.png" class="w-full h-full lg:max-w-lg">
    </section>
</template>

<script setup>

import { onMounted, ref } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const rightHero = ref(null)
const leftHero = ref(null)

gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = (element, {opacity, x, y}) => {
    gsap.fromTo(element, {opacity, x, y}, {
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
        }
    }) 
}

const animateOnDekstop = () => {
    animateOnScroll(rightHero.value, {opacity: 0, y: -50})
    leftHero.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 50})
    })
}

const animateOnMobile = () => {
    animateOnScroll(rightHero.value, {opacity: 0, y: 10})
    leftHero.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 10})
    })
}

onMounted(() => {
    const isDekstop = window.matchMedia("(min-width: 1024px)").matches
    isDekstop ? animateOnDekstop() : animateOnMobile()
});

</script>