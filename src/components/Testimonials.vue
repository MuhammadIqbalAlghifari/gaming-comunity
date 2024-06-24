<template>
    <section class="flex-col lg:p-20 md:p-14 max-w-screen-2xl mx-auto p-8 flex w-ful h-full justify-center items-center gap-y-10">
        <div class="flex-col flex justify-center items-center gap-y-5 lg:gap-y-10">
            <h1 ref="tittleOne" class="font-semibold lg:max-w-md text-center lg:text-4xl md:text-2xl text-xl text-white">Trusted by Thousand of Happy Customer</h1>
            <p ref="tittleTwo" class="lg:text-sm text-xs lg:max-w-md text-center text-white font-extralight">Lorem Ipsum is simply dummy text of printing and typesetting industry. Lorem Ipsum is simply.</p>
        </div>
        <div class="grid lg:grid-cols-3 grid-cols-1 md:grid-cols-2 w-full h-full lg:justify-between justify-center lg:items-start items-center lg:gap-x-10 lg:gap-y-0 md:gap-10 gap-y-5">
            <main v-for="(data, index) in testimonialsData" :key="index" ref="testimonials" class="flex-col w-full h-full flex justify-start items-start bg-[#1c1c1c] p-8 rounded-lg border-white gap-y-7 border-2 hover:border-orange-500 hover:transition-colors hover:duration-300">
                <div class="flex w-full h-auto justify-between items-center">
                    <div class="flex justify-center items-center gap-x-3">
                        <img :src="data.image" class="w-auto h-auto">
                        <div class="flex-col flex justify-center items-start gap-y-2">
                            <h1 class="text-white font-semibold lg:text-sm text-xs">{{ data.name }}</h1>
                            <p class="text-white font-extralight lg:text-sm text-xs"> {{ data.location }} </p>
                        </div>
                    </div>
                    <div class="flex justify-center items-center gap-x-2">
                        <p class="text-white lg:text-base text-sm">{{ data.rating }}</p>
                        <svg xmlns="http://www.w3.org/2000/svg" fill="yellow" viewBox="0 0 24 24" stroke-width="1.5" stroke="none" class="w-7 h-7">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499a.562.562 0 0 1 1.04 0l2.125 5.111a.563.563 0 0 0 .475.345l5.518.442c.499.04.701.663.321.988l-4.204 3.602a.563.563 0 0 0-.182.557l1.285 5.385a.562.562 0 0 1-.84.61l-4.725-2.885a.562.562 0 0 0-.586 0L6.982 20.54a.562.562 0 0 1-.84-.61l1.285-5.386a.562.562 0 0 0-.182-.557l-4.204-3.602a.562.562 0 0 1 .321-.988l5.518-.442a.563.563 0 0 0 .475-.345L11.48 3.5Z" />
                        </svg>
                    </div>
                </div>
                <p class="text-white lg:text-sm text-xs lg:text-start text-justify font-extralight">{{ data.description }}</p>
            </main>
        </div>
    </section>
</template>

<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { onMounted, ref } from 'vue';


const testimonialsData = [
    {
        image: "/Viezh Robert.png",
        name: "Viezh Robert",
        location: "Warsaw, Poland",
        rating: "4.5",
        description: "Lorem Ipsum is simply dummy text of printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s."
    },
    {
        image: "/Yessica Christy.png",
        name: "Yessica Christy",
        location: "Shanxi, China",
        rating: "4.5",
        description: "Lorem Ipsum is simply dummy text."
    },
    {
        image: "/kim young jon.png",
        name: "Kim Young Jou",
        location: "Seoul, South Korea",
        rating: "4.5",
        description: "Lorem Ipsum is simply dummy text of printing and typesetting industry."
    },
];

const tittleOne = ref(null)
const tittleTwo = ref(null)
const testimonials = ref([])

gsap.registerPlugin(ScrollTrigger)

const animateOnScroll = (element, {opacity, x, y}) => {
    gsap.fromTo(element, { opacity, x, y }, {
        opacity: 1,
        duration: 1,
        delay: 0.3,
        stagger: 0.2,
        x: 0,
        y: 0,
        ease: 'power3.out',
        scrollTrigger: {
            trigger: element,
            start: "top bottom",
            end: "center center",
        }
    })
}


onMounted(() => {
    animateOnScroll(tittleOne.value, {opacity: 0})
    animateOnScroll(tittleTwo.value, {opacity: 0})
    testimonials.value.forEach(child => {
        animateOnScroll(child, {opacity: 0, y: 50})
    })
})

</script>