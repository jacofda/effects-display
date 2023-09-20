<template>
  <div class="flex flex-col justify-center items-center h-screen bg-red-700 text-white">
    <h1 class="text-5xl mb-8">Testing horizontal scrolling w/ three sections</h1>
    <h2 class="text-3xl">First Container</h2>
  </div>
  <div class="horizontal-container mx-auto flex flex-nowrap h-screen text-white bg-primary">
    <template v-for="b of boxes" :key="b">
      <section class="panel border-transparent bg-primary w-screen flex items-center justify-end text-3xl h-screen">
        <h2 class="text-white">Panel {{ b }}</h2>
        <div class="bg-tertiary w-40 h-40 mr-32" :class="'box-' + b" />
      </section>
    </template>
  </div>
  <div class="bg-indigo-900 w-screen h-screen text-white flex items-center justify-center text-3xl">Last Container</div>
</template>

<script lang="ts" setup>
import gsap from 'gsap';

const boxes = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]);

definePageMeta({
  title: 'Secondo orizzontale',
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
  let scrollTween = gsap.to(sections, {
    xPercent: -100 * (sections.length - 1),
    ease: 'none',
    scrollTrigger: {
      trigger: '.horizontal-container',
      pin: true,
      scrub: 0.1,
      end: () => '+=' + end,

      // onEnter: () => {
      //   console.log('enter');
      // },
      // onLeave: () => {
      //   console.log('leave');
      // },
    },
  });

  // red section
  gsap.to('.box-1', {
    scale: 2,
    rotation: 360,
    duration: 3,
    scrollTrigger: {
      trigger: '.box-1',
      containerAnimation: scrollTween,
      start: 'left 70%',
      end: 'left 20%',
      scrub: 1,
    },
  });

  gsap.to('.box-2', {
    y: -100,
    scrollTrigger: {
      trigger: '.box-2',
      containerAnimation: scrollTween,
      start: 'left 70%',
      end: 'left 20%',
      scrub: 1,
    },
  });

  gsap.to('.box-3', {
    y: 100,
    scrollTrigger: {
      trigger: '.box-3',
      containerAnimation: scrollTween,
      start: 'left 70%',
      end: 'left 20%',
      scrub: 1,
    },
  });

  gsap.to('.box-4', {
    x: 100,
    scrollTrigger: {
      trigger: '.box-4',
      containerAnimation: scrollTween,
      start: 'left 70%',
      end: 'left 20%',
      scrub: 1,
    },
  });

  gsap.to('.box-5', {
    borderRadius: 200,
    x: 50,
    scrollTrigger: {
      trigger: '.box-5',
      containerAnimation: scrollTween,
      start: 'left 70%',
      end: 'left 20%',
      scrub: 1,
    },
  });

  let b6 = gsap.timeline({
    scrollTrigger: {
      trigger: '.box-6',
      containerAnimation: scrollTween,
      start: 'left 70%',
      end: 'left 20%',
      scrub: 1,
    },
  });
  b6.to('.box-6', {
    x: 100,
    y: 200,
  }).to('.box-6', {
    x: 0,
    y: 0,
  });
};
</script>
