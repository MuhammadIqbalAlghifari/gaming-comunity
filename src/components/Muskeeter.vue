<template>
    <section class="lg:p-20 md:p-14 p-12 flex flex-col max-w-screen-2xl mx-auto lg:flex-row gap-y-10 lg:gap-y-0 w-full justify-between items-center">
        <img ref="leftHero" src="/muskeeter-about.png" class="w-full h-full object-cover lg:max-w-lg">
        <article ref="rightHero" class="flex-col flex justify-center lg:items-start items-center lg:gap-y-10 gap-y-5">
            <p class="text-white lg:text-sm text-xs">Lorem Ipsum</p>
            <h1 class="text-white lg:text-2xl md:text-xl text-lg lg:text-start text-center font-bold max-w-md leading-loose lg:leading-loose">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</h1>
            <p class="text-white lg:text-sm text-xs lg:text-start text-center max-w-lg leading-loose">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy test ever since 1500s, when an unknown printer took a gailwy of type and scrambled it to make a type specimen book. it has survived not only five centuries.</p>
        </article>
    </section>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const leftHero = ref(null)
const rightHero = ref(null)

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
    animateOnScroll(leftHero.value, {opacity: 0, y: 50})
    rightHero.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 50})
    })
}

const animateOnMobile = () => {
    animateOnScroll(leftHero.value, {opacity: 0, y: 50})
    rightHero.value.childNodes.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 50})
    })
}

onMounted(() => {
    const isDekstop = window.matchMedia("(min-width: 1024px)").matches
    isDekstop ? animateOnDekstop() : animateOnMobile()
});
</script>
