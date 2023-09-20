<template>
  <section class="h-screen grid place-content-center">
    <h1 class="text-3xl">Scroll down for effects</h1>
  </section>

  <section class="h-screen grid place-content-center border-b-gray-950">
    <p class="reveal-type" data-bg-color="#ffffff" data-fg-color="#000000">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores
    </p>
  </section>
  <section class="h-screen grid place-content-center bg-yellow-300">
    <p class="reveal-type" data-bg-color="#fde047" data-fg-color="#000000">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores
    </p>
  </section>
  <section class="h-screen grid place-content-center bg-gray-900 text-white">
    <p class="reveal-type" data-bg-color="#cccccc" data-fg-color="red">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores
    </p>
  </section>
  <section class="h-screen"></section>
</template>

<script lang="ts" setup>
import gsap from 'gsap';
import SplitType from 'split-type';

definePageMeta({
  title: 'Primo testo',
});

useHead({
  bodyAttrs: {
    class: `overflow-hidden`,
  },
  title: 'Primo testo',
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
  const splitTypes = document.querySelectorAll('.reveal-type');
  splitTypes.forEach((char, i) => {
    const bg = (char as HTMLElement).dataset.bgColor;
    const fg = (char as HTMLElement).dataset.fgColor;
    const text = new SplitType(char as HTMLElement, { types: 'chars' });
    gsap.fromTo(
      text.chars,
      {
        color: bg,
        //   scaleY: 0,
        //   y: -20,
        //   transformOrigin: 'top',
      },
      {
        color: fg,
        //   scaleY: 1,
        //   y: 0,
        // duration: 0.3,
        stagger: 0.02,
        scrollTrigger: {
          trigger: char,
          start: 'top 80%',
          end: 'bottom 20%',
          scrub: 0.1,
          // toggleActions: 'play play reverse reverse',
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
