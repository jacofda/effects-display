<template>
  <section class="h-screen grid place-content-center">
    <h1 class="text-3xl">Scroll down for effects</h1>
  </section>

  <section class="h-screen grid place-content-center bg-primary text-white">
    <p class="reveal-type">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores</p>
  </section>
  <section class="h-screen grid place-content-center bg-tertiary">
    <p class="reveal-type">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores</p>
  </section>
  <section class="h-screen grid place-content-center bg-secondary text-black">
    <p class="reveal-type">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores</p>
  </section>
  <section class="h-screen"></section>
</template>

<script lang="ts" setup>
import gsap from 'gsap';
import SplitType from 'split-type';

definePageMeta({
  title: 'Secondo testo',
});

useHead({
  bodyAttrs: {
    class: `overflow-hidden`,
  },
  title: 'Secondo testo',
});

onMounted(() => {
  animations();
});

const animations = () => {
  const splitTypes = document.querySelectorAll('.reveal-type');
  splitTypes.forEach((char, i) => {
    const text = new SplitType(char as HTMLElement, { types: 'chars' });
    gsap.fromTo(
      text.chars,
      {
        opacity: 0,
        scale: 2,
        y: -20,
        transformOrigin: 'top',
      },
      {
        opacity: 1,
        scale: 1,
        y: 0,
        stagger: 0.02,
        scrollTrigger: {
          trigger: char,
          start: 'top 80%',
          end: 'bottom 20%',
          scrub: 0.1,
        },
      }
    );
  });
};
</script>

<style scoped>
section {
  padding: 0 clamp(4rem, 12vw, 20rem);
}

section p {
  font-size: clamp(2rem, 5vw, 8rem);
}
</style>
