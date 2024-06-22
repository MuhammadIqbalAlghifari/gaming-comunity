<template>
    <section class="lg:p-20 md:p-14 p-12 flex max-w-screen-2xl mx-auto flex-col justify-center items-center gap-y-10">
        <h1 ref="tittle" class="text-white font-semibold text-2xl text-center">Our Team</h1>
        <div class="flex flex-col lg:flex-row gap-y-10 lg:gap-y-0 w-full justify-between gap-x-10 items-center">
            <main v-for="(data, index) in ourTeam" :key="index" ref="teamList" class="flex rounded-xl w-full flex-col justify-center items-center bg-[#1c1c1c] p-10 gap-y-5">
                <img :src="data.image" alt="">
                <h1 class="text-white text-base font-semibold">John Doe</h1>
                <h1 class="text-white text-base">CEO</h1>
            </main>
        </div>
    </section>
</template>
<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { onMounted, ref } from 'vue';


const ourTeam = [
    {
        image: "/Bill 1.png",
    },
    {
        image: "/Beverly 1.png",
    },
    {
        image: "/Claudia 1.png",
    },
    {
        image: "/Avatar 1.png",
    },
]

const tittle = ref(null)
const teamList = ref([])

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
    teamList.value.forEach(child => {
        gsap.fromTo(child, { opacity: 0, y: 50 }, { opacity: 1, y: 0, duration: 1, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
            trigger: child,
            start: 'top bottom',
            end: 'center center'
        }})
    })
    gsap.fromTo(tittle.value, { opacity: 0 }, { opacity: 1, duration: 1, stagger: 0.3, delay: 0.2, ease: 'power3.out', scrollTrigger: {
        trigger: tittle.value,
        start: 'top bottom',
        end: 'center center'
    }})
})

</script>