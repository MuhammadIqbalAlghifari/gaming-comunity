<template>
    <section ref="footer" class="bg-black pt-10 flex flex-col justify-center items-center w-full">
        <div class="flex flex-wrap gap-10 lg:gap-0 lg:px-16 px-12 md:px-14 justify-between items-start h-auto w-full">
            <div class="flex flex-col gap-y-6 justify-center items-start">
                <h1 class="lg:text-xl text-lg text-white font-bold">LOGO</h1>
                <p class="text-white lg:text-sm text-xs max-w-xs">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
                <p class="text-white lg:text-sm text-xs">@Logo</p>
            </div>
            <div class="flex flex-col gap-y-6 justify-center items-start">
                <h1 class="text-base text-white">About Us</h1>
                <div class="flex flex-col gap-y-1.5 justify-center items-start">
                    <p class="text-white lg:text-sm text-xs">Zeus</p>
                    <p class="text-white lg:text-sm text-xs">Portfolio</p>
                    <p class="text-white lg:text-sm text-xs">Careers</p>
                    <p class="text-white lg:text-sm text-xs">Contact Us</p>
                </div>
            </div>
            <div class="flex flex-col gap-y-6 justify-center items-start">
                <h1 class="text-base text-white">Contact Us</h1>
                <p class="text-white lg:text-sm text-xs max-w-[16rem]">Lorem Ipsum is simply dummy text of the printing and typesetting industry.</p>
                <p class="text-white lg:text-sm text-xs">+62 8579 5635 990</p>
            </div>
            <!-- Logo -->
        </div>
        <hr class="w-full h-0.5 bg-white mt-10"/>
        <p class="text-white lg:text-sm text-xs py-10">Copyright ® {{ currentYear }} Lorem All rights reserved</p>
    </section>
</template>
<script setup>

import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { onMounted, ref } from 'vue';

const footer = ref(null)

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    footer.value.childNodes.forEach(child => {
        gsap.fromTo(child, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, ease: 'power3.out', stagger: 0.3, delay: 0.2, scrollTrigger: {
            trigger: child,
            start: 'top bottom',
            end: "center center"
        }})
    })
})

</script>