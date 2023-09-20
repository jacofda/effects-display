<template>
  <section class="h-screen grid place-content-center">
    <h1 class="text-3xl">Scroll down for effects</h1>
  </section>
  <!-- <section class="grid grid-cols-3 h-screen mx-auto my-0">
    <div class="border border-transparent border-r-gray-950"></div>
    <div class="border border-transparent border-r-gray-950"></div>
    <div class=""></div>
  </section> -->
  <section class="grid grid-cols-3 h-screen mx-auto my-0">
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/1.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/2.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/3.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/4.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/5.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/6.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/7.webp')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/8.webp')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/9.webp')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/10.webp')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/5.png')"></div>
    <div class="img w-full h-[500px] relative bg-cover -z-10" style="background-image: url('/assets/6.png')"></div>
  </section>
</template>

<script lang="ts" setup>
import gsap from 'gsap';
import SplitType from 'split-type';

definePageMeta({
  title: 'Primo galleria',
});

useHead({
  bodyAttrs: {
    class: `overflow-hidden`,
  },
  title: 'Primo galleria',
});

useHead({
  bodyAttrs: {
    class: `overflow-hidden`,
  },
});

onMounted(() => {
  animations();
});

const animations = () => {
  const tl = gsap
    .timeline({
      scrollTrigger: {
        trigger: '.img',
        scrub: 0.1,
      },
    })
    .to('.img', {
      stagger: 0.2,
      y: -500,
      scrub: 0.1,
    });
};
</script>
