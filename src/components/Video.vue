<template>
    <section class="lg:p-20 md:p-14 p-12 max-w-screen-2xl mx-auto flex flex-wrap lg:flex-nowrap lg:justify-between justify-center gap-y-5 lg:gap-y-0 items-center w-full">
        <img ref="leftHero" src="/hero-video.png" class="w-full cursor-pointer h-full lg:max-w-2xl"/>
        <article ref="rightHero" class="flex flex-col justify-center lg:items-start items-center md:gap-y-5 gap-y-3 w-full lg:max-w-md">
            <h1 class="font-bold lg:leading-relaxed leading-relaxed lg:text-4xl md:text-2xl text-xl text-white">Lorem Ipsum is simply dummy text.</h1>
            <p class="lg:leading-loose leading-loose text-white lg:text-base text-xs lg:text-start text-center font-extralight">Lorem Ipsum is simply dummy text of the printing and typesetting industry Lorem Ipsum is simply dummy.</p>
                <div ref="checkList" class="flex flex-col justify-center items-start gap-y-5">
                    <div class="flex justify-start items-center gap-x-3">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="black" class="md:size-6 size-5 p-0.5 bg-green-500 rounded-full">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>
                        <p class="text-white lg:text-base text-xs font-extralight">Lorem Ipsum is simply</p>
                    </div>
                    <div class="flex justify-start items-center gap-x-3">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="black" class="md:size-6 size-5 p-0.5 bg-green-500 rounded-full">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>
                        <p class="text-white lg:text-base text-xs font-extralight">Lorem Ipsum is simply</p>
                    </div>
                    <div class="flex justify-start items-center gap-x-3">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="black" class="md:size-6 size-5 p-0.5 bg-green-500 rounded-full">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>
                        <p class="text-white lg:text-base text-xs font-extralight">Lorem Ipsum is simply</p>
                    </div>
                    <div class="flex justify-start items-center gap-x-3">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="black" class="md:size-6 size-5 p-0.5 bg-green-500 rounded-full">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>
                        <p class="text-white lg:text-base text-xs font-extralight">Lorem Ipsum is simply</p>
                    </div>
                </div>
        </article>        
    </section>
</template>

<script setup>

import { onMounted, ref } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const leftHero = ref(null)
const rightHero = ref(null)
const checkList = ref(null)

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
    animateOnScroll(leftHero.value, {opacity: 0, y: -50})
    rightHero.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 50})
    })
    checkList.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 50})
    })
}

const animateOnMobile = () => {
    animateOnScroll(leftHero.value, {opacity: 0, y: 10})
    rightHero.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 10})
    })
    checkList.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 10})
    })
}

onMounted(() => {
    const isDekstop = window.matchMedia("(min-width: 1024px)").matches
    isDekstop ? animateOnDekstop() : animateOnMobile()
});

</script>