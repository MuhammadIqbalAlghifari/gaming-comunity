<template>
    <main class="w-full lg:h-screen h-full max-w-screen-2xl mx-auto flex flex-wrap justify-between lg:px-20 lg:py-0 md:pt-24 md:px-14 pt-20 px-8 items-center">
        <div ref="leftHero" class="flex lg:w-1/2 w-full flex-col justify-center items-center gap-y-4 lg:items-start">
            <p class="text-orange-600 lg:text-base md:text-sm text-xs font-bold">3D game dev</p>
            <h1 class="text-white lg:text-5xl md:text-3xl text-xl max-w-sm leading-normal lg:leading-normal text-center lg:text-start font-bold">Work that we produce for our clients</h1>
            <p class="text-white lg:text-sm text-xs lg:text-start text-center max-w-lg lg:max-w-none lg:leading-loose leading-loose">Lorem Ipsum is sipmly dummy text for printing and <br class="hidden lg:block"> typesetting industry. Lorem Ipsum has been the industry's <br class="hidden lg:block"> standard.</p>
            <button class="bg-orange-500 lg:px-8 lg:py-4 px-6 py-2 lg:text-sm text-xs rounded-full text-white">Get more details</button>
        </div>
        <div ref="rightHero" class="lg:w-1/2 lg:py-0 py-5 w-full h-full relative flex justify-center">
            <img src="/joy-stick.png" alt="" class="w-[80%] -z-10 h-full">
            <div class="w-full flex flex-col justify-end gap-y-10 items-center md:h-[50%] h-[55%] absolute z-10">
                <div class="w-[75%] flex justify-between items-center">
                    <img src="/cry-engine.png" alt="" class="md:w-auto md:h-auto w-auto h-auto object-cover md:object-none">
                    <img src="/unreal.png" alt="" class="md:w-auto md:h-auto w-auto h-auto object-cover md:object-none">
                </div>
                <div class="w-full lg:-ml-40 flex justify-start">
                    <img src="/unity.png" alt="" class="md:w-auto md:h-auto w-auto h-auto object-cover md:object-none">
                </div>
            </div>
        </div>
    </main>
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
        delay: 0.2,
        ease: 'power3.out',
    }) 
}

const animateOnDekstop = () => {
    animateOnScroll(leftHero.value.children, {opacity: 0})
    animateOnScroll(rightHero.value.children, {opacity: 0, y: 1000})
}

const animateOnMobile = () => {
    animateOnScroll(leftHero.value.children, {opacity: 0, y: 10})
    animateOnScroll(rightHero.value.children, {opacity: 0, y: 1000})
}

onMounted(() => {
    const isDekstop = window.matchMedia("(min-width: 1024px)").matches
    isDekstop ? animateOnDekstop() : animateOnMobile()
});

</script>