<template>
    <section class="lg:p-20 md:p-14 p-8 flex flex-wrap lg:flex-nowrap max-w-screen-2xl mx-auto lg:justify-between justify-center lg:items-start items-center w-full h-auto gap-y-5 lg:gap-x-10">
        <div class="flex-col flex w-full lg:w-auto justify-center h-full lg:items-start items-center lg:gap-y-10 gap-y-5">
            <main v-for="(data, index) in leftNews" :key="index" ref="leftArticle" class="flex-col lg:max-w-xl w-full flex justify-center lg:items-start items-center gap-y-5">
                <div class="flex-col flex justify-center lg:items-start items-center lg:gap-y-5 gap-y-3">
                    <img :src="data.image" alt="" class="w-full h-auto rounded-lg">
                    <div class="flex justify-center items-center gap-x-3">
                        <p class="bg-blue-500 px-6 py-2 text-white lg:text-base text-xs">{{ data.author }}</p>
                        <p class="text-white text-center lg:text-start lg:text-base text-xs">{{ data.time }}</p>
                    </div>
                </div>
                <div class="flex flex-col justify-center lg:items-start items-center gap-y-4 lg:gap-y-7 lg:max-w-lg">
                    <h1 class="lg:text-2xl text-xl font-semibold text-white text-center lg:text-start lg:max-w-lg leading-relaxed lg:leading-relaxed">{{ data.tittle }}</h1>
                    <p class="lg:text-base text-sm font-extralight text-white lg:text-start text-justify lg:max-w-lg leading-loose lg:leading-loose">{{ data.descOne }}</p>
                    <p class="lg:text-base text-sm font-extralight text-white leading-relaxed lg:leading-relaxed lg:max-w-md">{{ data.descTwo }}</p>
                </div>
                <hr class="w-full h-1 bg-white lg:my-10 my-3">
            </main>
        </div>
        <div class="flex-col flex justify-center h-auto lg:items-start items-center lg:gap-y-10 gap-y-5">
            <main v-for="(data, index) in rightNews" :key="index" ref="rightArticle" class="flex flex-wrap lg:flex-nowrap lg:max-w-xl w-full justify-center items-center lg:items-start lg:gap-x-5 gap-y-5">
                <img :src="data.image" alt="" class="lg:w-auto lg:h-auto w-full h-full rounded-lg">
                <div class="flex-col flex justify-center lg:items-start items-center gap-y-5">
                    <div class="flex justify-center items-center gap-x-3">
                        <p class="bg-blue-500 px-6 py-2 text-center lg:text-start text-white lg:text-sm text-xs">{{ data.author }}</p>
                        <p class="text-white lg:text-sm text-xs">{{ data.time }}</p>
                    </div>
                    <h1 class="lg:text-xl text-lg font-semibold text-white text-center lg:text-start lg:max-w-2xl leading-relaxed lg:leading-relaxed">{{ data.tittle }}</h1>
                </div>
                <hr class="w-full h-1 bg-white lg:hidden lg:my-10 my-3">
            </main>
        </div>
    </section>
</template>

<script setup>

import { onMounted, ref } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const leftNews = [
    {
        image: "/muskeeter-news.png",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text",
        descOne: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. it has survived not only five centuries,",
        descTwo: "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    },
    {
        image: "/limbo-punk-news.png",
        author: "John Doe",
        time: "10 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text",
        descOne: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. it has survived not only five centuries,",
        descTwo: ""
    },
];

const rightNews = [
    {
        image: "/news-1.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
    {
        image: "/news-2.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
    {
        image: "/news-3.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
    {
        image: "/news-4.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
    {
        image: "/news-5.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
    {
        image: "/news-6.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
    {
        image: "/news-7.jpg",
        author: "John Doe",
        time: "5 minutes ago",
        tittle: "Lorem Ipsum is simply dummy text dummy text?",
    },
];


const leftArticle = ref([])
const rightArticle = ref([])

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

onMounted(() => {
    leftArticle.value.forEach(child => {
        animateOnScroll(child, { opacity: 0, y: 50 })
    }) 
    rightArticle.value.forEach(child => {
        animateOnScroll(child, { opacity: 0, y: 50 })
    }) 
});

</script>