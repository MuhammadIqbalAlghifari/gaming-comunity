<template>
    <section class="lg:p-20 md:p-14 p-8 w-full max-w-screen-2xl mx-auto">
        <div ref="contactUs" class="flex flex-col gap-y-1.5 md:gap-3 lg:gap-y-5 py-5 justify-center lg:items-start items-center">
            <h1 class="text-white lg:text-3xl md:text-xl text-base tracking-wide leading-loose font-medium">Lorem Ipsum</h1>
            <p class="text-white lg:text-sm text-xs tracking-wide max-w-lg lg:text-left text-center leading-loose lg:leading-loose">Lorem Ipsum is simply dummy text of the printing and typersetting industry.</p>
            <div class="md:p-10 px-3 py-5 my-6 bg-slate-200 bg-opacity-5 w-full rounded-lg">
                <div class="flex flex-wrap w-full lg:justify-between justify-center lg:items-center gap-5">
                    <div class="flex flex-col justify-center gap-y-1.5 lg:gap-y-5 lg:items-start items-center">
                        <h1 class="text-white lg:text-3xl md:text-xl text-base tracking-wide leading-loose font-medium">Stay in the loop</h1>
                        <p class="text-white lg:text-sm text-xs tracking-wide max-w-md lg:text-left text-center leading-loose lg:leading-loose">Subscribe to receive the latest news and updates about TDA. We promise not to spam you!</p>
                    </div>
                    <div class="bg-white lg:p-1.5 p-0.5 rounded-md flex justify-center items-center">
                        <input type="text" placeholder="Enter email address" class="lg:text-sm text-[8px] w-auto focus:outline-none sm:px-6 px-3 text-gray-700">
                        <button class="bg-orange-500 sm:p-3 p-1.5 rounded-md text-white lg:text-sm text-[8px]">Continue</button>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>

import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { onMounted, ref } from 'vue';

const contactUs = ref(null)

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    contactUs.value.childNodes.forEach(child => {
        gsap.fromTo(child, {opacity: 0, y: 50}, {opacity: 1, y: 0, duration: 1, ease: 'power3.out', stagger: 0.3, delay: 0.2, scrollTrigger: {
            trigger: child,
            start: 'top bottom',
            end: "center center"
        }})
    })
})

</script>