<template>
  <div class="flex flex-col justify-center items-center h-screen bg-red-700 text-white">
    <h1 class="text-5xl mb-8">Testing horizontal scrolling w/ three sections</h1>
    <h2 class="text-3xl">First Container</h2>
  </div>
  <div class="horizontal-container mx-auto flex flex-nowrap h-screen text-white">
    <div class="description panel bg-blue-900 w-screen flex items-center justify-center text-3xl">ONE</div>

    <section class="panel bg-green-900 w-screen flex items-center justify-center text-3xl">TWO</section>
    <section class="panel bg-gray-600 w-screen flex items-center justify-center text-3xl">THREE</section>
    <section class="panel bg-purple-900 w-screen flex items-center justify-center text-3xl">FOUR</section>
  </div>
  <div class="bg-indigo-900 w-screen h-screen text-white flex items-center justify-center text-3xl">Last Container</div>
</template>

<script lang="ts" setup>
import gsap from 'gsap';

definePageMeta({
  title: 'Primo orizzontale',
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
  let sections = gsap.utils.toArray('.panel');
  gsap.set('.horizontal-container', {
    width: sections.length * 100 + 'vw',
  });

  if (document.querySelector('.horizontal-container') === null) return;

  let end = document.querySelector<HTMLElement>('.horizontal-container')?.offsetWidth;
  gsap.to(sections, {
    xPercent: -100 * (sections.length - 1),
    // ease: 'none',
    scrollTrigger: {
      trigger: '.horizontal-container',
      pin: true,
      scrub: true,
      snap: 1 / (sections.length - 1),
      end: () => '+=' + end,

      // onEnter: () => {
      //   console.log('enter');
      // },
      // onLeave: () => {
      //   console.log('leave');
      // },
    },
  });
};
</script>
