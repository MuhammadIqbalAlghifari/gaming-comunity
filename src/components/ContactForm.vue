<template>
    <section class="lg:p-20 p-12 md:p-14 flex flex-col max-w-screen-2xl mx-auto justify-center w-full items-center gap-y-10">
        <div ref="tittle" class="flex-col flex justify-center items-center gap-y-4">
            <h1 class="lg:text-4xl md:text-2xl text-xl text-white text-center">Say Hello</h1>
            <p class="lg:text-base text-sm text-white">Lorem Ipsum is simply dummy text of the printing.</p>
        </div>
        <form ref="formInput" class="flex-col justify-center items-center w-full max-w-3xl flex gap-y-5">
            <div class="flex justify-center items-center w-full gap-x-5">
                <div class="flex-col flex justify-center items-start gap-y-3 w-full">
                    <label class="text-white lg:text-sm text-xs font-extralight">First name</label>
                    <input type="text" placeholder="First name" class="w-full h-14 focus p-4 focus:outline-orange-500 bg-[#1c1c1c] rounded-lg lg:text-sm text-xs backdrop-blur-md transition-all duration-300">
                </div>
                <div class="flex-col flex justify-center items-start gap-y-3 w-full">
                    <label class="text-white lg:text-sm text-xs font-extralight">Last name</label>
                    <input type="text" placeholder="Last name" class="w-full h-14 focus p-4 focus:outline-orange-500 bg-[#1c1c1c] rounded-lg lg:text-sm text-xs backdrop-blur-md transition-all duration-300">
                </div>
            </div>
            <div class="flex-col flex justify-center items-start gap-y-3 w-full">
                <label class="text-white lg:text-sm text-xs font-extralight">Email Address</label>
                <input type="text" placeholder="Email" class="w-full h-14 focus p-4 focus:outline-orange-500 bg-[#1c1c1c] rounded-lg lg:text-sm text-xs backdrop-blur-md transition-all duration-300">
            </div>
            <div class="flex-col flex justify-center items-start gap-y-3 w-full">
                <label class="text-white lg:text-sm text-xs font-extralight">Message</label>
                <textarea type="text" placeholder="Message" class="w-full h-32 focus p-4 focus:outline-orange-500 bg-[#1c1c1c] rounded-lg lg:text-sm text-xs backdrop-blur-md transition-all duration-300"/>
            </div>
            <button class="lg:px-6 lg:py-3 px-4 py-2 rounded-lg bg-[#1c1c1c] text-white lg:text-base text-sm font-extralight hover:bg-orange-500 hover:font-normal hover:transition-all hover:duration-300">SEND MESSAGE</button>
        </form>
    </section>
</template>

<script setup>

import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { onMounted, ref } from 'vue';

const tittle = ref(null)
const formInput = ref(null)

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    gsap.fromTo(tittle.value.children, { opacity: 0 }, { opacity: 1, duration: 1, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: tittle.value.children,
        start: "top bottom",
        end: 'center center'
    }})
    
    formInput.value.childNodes.forEach(child => {
        gsap.fromTo(child, { opacity: 0, y: 50 }, { opacity: 1, y: 0, duration: 1, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
            trigger: child,
            start: "top bottom",
            end: 'center center'
        }})
    })
})

</script>