<template>
    <main class="relative w-full h-full max-w-screen-2xl lg:my-20 md:my-14 my-8 mx-auto">
        <img src="/service.jpg" class="w-full h-full blur-[2px] absolute -z-10 object-cover brightness-[20%]">
        <div class="py-20 px-10">
            <div ref="tittle" class="flex flex-col justify-center items-center gap-y-4">
                <h1 class="text-white lg:text-3xl md:text-xl text-base mx-auto lg:tracking-wide tracking-wide text-center lg:leading-loose leading-loose max-w-4xl font-semibold">Lorem Ipsum is simply dummy text of the printing and typersetting industry.</h1>
                <p class="text-white lg:text-base text-sm lg:tracking-wide tracking-wide max-w-3xl text-center lg:leading-loose leading-loose">Lorem Ipsum is simply dummy text of the printing and typersetting industry. Lorem Ipsum has been industry's standard dummy text since 1500's.</p>
            </div>
            <div class="flex px-10 flex-col gap-y-5 md:gap-y-10 justify-center w-full py-20 items-center">
                <div ref="sectionOne" class="flex flex-col md:flex-row md:justify-between justify-center gap-y-5 md:gap-y-0 items-center w-full">
                    <div class="flex flex-col justify-center items-center lg:gap-y-7 gap-y-5">
                        <svg class="text-white md:w-14 md:h-14 w-12 h-12" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16">
                            <path fill="currentColor" d="M12 0H3c-.55 0-1 .45-1 1v14c0 .55.45 1 1 1h9c.55 0 1-.45 1-1V1c0-.55-.45-1-1-1M7.5 15.278a.778.778 0 1 1 0-1.555a.778.778 0 0 1 0 1.555M12 13H3V2h9z"/>
                        </svg>
                        <p class="text-white text-center text-base font-semibold">Mobile Game Development</p>
                        <!-- Arrow here -->
                    </div>
                    <div class="flex flex-col justify-center items-center gap-y-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 512 512">
                            <path fill="currentColor" d="M29.65 117.89v276.22h124.62V117.89zm90.55 253.16a11 11 0 1 1 11-11a11 11 0 0 1-11 11m18-189.16H45.56v-16h92.63v16zm0-32H45.56v-16h92.63v16zm153 188.51h73.1v39.71h41.74v16H249.48v-16h41.74V338.4zm-118-220.51V322.4h309.15V117.89H173.19zM466.35 306.4H189.19V133.89h277.16z"/>
                        </svg>
                        <p class="text-white text-center text-base font-semibold">PC Game Development</p>
                        <!-- Arrow here -->
                    </div>
                    <div class="flex flex-col justify-center items-center gap-y-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 32 32">
                            <path fill="currentColor" d="M16.407 17.573V14.39c0-.651.301-1.115.948-1.115h3.989c.02 0 .047-.021.047-.047v-.636c0-.005 0-.009-.005-.015h-4.88c-1.057.135-1.573.875-1.573 1.812v3.183c0 .64-.312 1.109-.948 1.109H9.782c-.027 0-.047.015-.047.047v.635c0 .027.011.048.025.052h4.781c1.245-.036 1.86-.828 1.86-1.848zM.031 19.421h1.401a.056.056 0 0 0 .037-.057v-2.025c0-.651.364-1.099.9-1.099h5.767c1.296 0 1.927-.797 1.927-1.844c0-.943-.516-1.677-1.573-1.812H.011c0 .004-.011.009-.011.015v.636c0 .031.016.047.047.047h7.599c.647 0 .948.464.948 1.109s-.301 1.115-.948 1.115H1.637c-.933 0-1.636.792-1.636 1.833v2.025c0 .027.016.048.036.052zm21.333-.733h7.657c.02 0 .041.015.041.031v.645c0 .032.02.048.041.048h1.38c.027 0 .052-.016.052-.048v-.635c0-.027.027-.047.052-.047h1.371c.031 0 .047-.027.047-.047v-.647c0-.025-.011-.052-.047-.052h-1.371c-.025 0-.052-.02-.052-.041v-4.62c0-.375-.135-.615-.375-.697h-.396a1.85 1.85 0 0 0-.405.176l-8.24 5.089c-.323.203-.432.427-.355.593c.063.141.251.245.604.245zm1.199-.849l6.385-3.953c.041-.031.12-.021.12.068v3.948c0 .025-.021.047-.041.047h-6.428c-.052 0-.077-.016-.083-.031c-.011-.032.005-.057.047-.079"/>
                        </svg>
                        <p class="text-white text-center text-base font-semibold">PS4 Game Development</p>
                        <!-- Arrow here -->
                    </div>
                    <div class="flex flex-col justify-center items-center gap-y-4">
                        <div class="flex justify-center items-center gap-x-0.5">
                            <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 24 24">
                                <path fill="currentColor" d="M5 3a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V5a2 2 0 0 0-2-2zm2 6h3c.6 0 1 .5 1 1v5H9.5v-1.5h-2V15H6v-5c0-.5.4-1 1-1m6 0h3.5c.85 0 1.5.65 1.5 1.5v1c0 .6-.4 1.15-.9 1.4L18 15h-1.5l-.85-2H14.5v2H13zm-5.5 1.5V12h2v-1.5zm7 0v1h2v-1z"/>
                            </svg>
                            <span class="text-white text-base font-semibold">/</span>
                            <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 24 24">
                                <path fill="currentColor" d="M5 3a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V5a2 2 0 0 0-2-2zm1 6h1.5l1 3.43L9.5 9H11l-1.75 6h-1.5zm7 0h3.5c.85 0 1.5.65 1.5 1.5v1c0 .6-.4 1.15-.9 1.4L18 15h-1.5l-.85-2H14.5v2H13zm1.5 1.5v1h2v-1z"/>
                            </svg>
                        </div>
                        <p class="text-white text-center text-base font-semibold">AR/VR Solutions</p>
                        <!-- Arrow here -->
                    </div>
                </div>
                <div ref="sectionTwo" class="flex flex-col md:flex-row md:justify-between max-w-md justify-center gap-y-5 md:gap-y-0 items-center w-full">
                    <div class="flex flex-col justify-center items-center gap-y-4">
                        <div class="flex justify-center items-center gap-x-0.5">
                            <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 24 24">
                                <path fill="currentColor" d="M5 3a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V5a2 2 0 0 0-2-2zm2 6h3c.6 0 1 .5 1 1v5H9.5v-1.5h-2V15H6v-5c0-.5.4-1 1-1m6 0h3.5c.85 0 1.5.65 1.5 1.5v1c0 .6-.4 1.15-.9 1.4L18 15h-1.5l-.85-2H14.5v2H13zm-5.5 1.5V12h2v-1.5zm7 0v1h2v-1z"/>
                            </svg>
                            <span class="text-white text-base font-semibold">/</span>
                            <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 24 24">
                                <path fill="currentColor" d="M5 3a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V5a2 2 0 0 0-2-2zm1 6h1.5l1 3.43L9.5 9H11l-1.75 6h-1.5zm7 0h3.5c.85 0 1.5.65 1.5 1.5v1c0 .6-.4 1.15-.9 1.4L18 15h-1.5l-.85-2H14.5v2H13zm1.5 1.5v1h2v-1z"/>
                            </svg>
                        </div>
                        <p class="text-white text-center text-base font-semibold">AR/VR Design</p>
                        <!-- Arrow here -->
                    </div>
                    <div class="flex flex-col justify-center items-center gap-y-4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="text-white md:w-14 md:h-14 w-12 h-12" viewBox="0 0 16 16">
                            <g fill="currentColor">
                                <path d="M4.52 8.368h.664c.646 0 1.055.378 1.06.9c.008.537-.427.919-1.086.919c-.598-.004-1.037-.325-1.068-.756H3c.03.914.791 1.688 2.153 1.688c1.24 0 2.285-.66 2.272-1.798c-.013-.953-.747-1.38-1.292-1.432v-.062c.44-.07 1.125-.527 1.108-1.375c-.013-.906-.8-1.57-2.053-1.565c-1.31.005-2.043.734-2.074 1.67h1.103c.022-.391.383-.751.936-.751c.532 0 .928.33.928.813c.004.479-.383.835-.928.835h-.632v.914zm3.606-3.367V11h2.189C12.125 11 13 9.893 13 7.985c0-1.894-.861-2.984-2.685-2.984zm1.187.967h.844c1.112 0 1.621.686 1.621 2.04c0 1.353-.505 2.02-1.621 2.02h-.844z"/>
                                <path d="M14 3a1 1 0 0 1 1 1v8a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1V4a1 1 0 0 1 1-1zM2 2a2 2 0 0 0-2 2v8a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V4a2 2 0 0 0-2-2z"/>
                            </g>
                        </svg>
                        <p class="text-white text-center text-base font-semibold">3D Modelings</p>
                        <!-- Arrow here -->
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

const sectionOne = ref(null);
const sectionTwo = ref(null);
const tittle = ref(null)

const animateOnScroll = (element, { opacity, x, y }) => {
  gsap.fromTo(element, { opacity, x, y }, {
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
      },
    }
  );
};

onMounted(() => {
  sectionOne.value.childNodes.forEach(card => {
    animateOnScroll(card, { opacity: 0, y: 50 });
  });
  sectionTwo.value.childNodes.forEach(card => {
    animateOnScroll(card, { opacity: 0, y: 50 });
  });
  animateOnScroll(tittle.value.children, {opacity: 0})
});
</script>