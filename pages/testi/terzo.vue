<template>
  <section class="h-screen grid place-content-center">
    <h1 class="text-3xl">Scroll down for effects</h1>
  </section>

  <section class="h-full grid place-content-center bg-primary text-white">
    <p class="reveal-type pt-40 pb-60">
      Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem
      aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo
      enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui
      ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur,
      adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat
      voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut
      aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil
      molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur? Sed ut perspiciatis unde
      omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab
      illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia
      voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi
      nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia
      non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima
      veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur?
      Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur, vel illum
      qui dolorem eum fugiat quo voluptas nulla pariatur? orem ipsum dolor sit amet, consectetur adipiscing elit. Fusce
      nisi sapien, pharetra in interdum vel, commodo consectetur erat. Nam consequat facilisis lectus, ut finibus ex
      ullamcorper eu. In mi mauris, pretium ut finibus in, consectetur in urna. Mauris malesuada laoreet tristique.
      Quisque aliquam urna id turpis scelerisque lacinia. Aliquam cursus iaculis lacus et cursus. Nam vitae efficitur
      elit. Vestibulum vitae sem eu tellus venenatis fermentum ut sit amet orci. Etiam porta sapien eget ullamcorper
      tincidunt. Etiam a velit ornare, consequat magna ac, dignissim felis. Nam at odio quis velit suscipit
      pellentesque. Donec varius a mi eu imperdiet. Vivamus vel elit quis neque vulputate iaculis mattis ac quam.
      Vestibulum in mauris eget est pretium scelerisque. Sed convallis quis ipsum mollis congue. Vivamus nec metus nisl.
      Nulla at ligula quis magna pretium dictum. Mauris sagittis enim a sollicitudin consequat. Nunc ac nisl sit amet
      mauris vestibulum viverra nec non tortor. Donec laoreet fringilla nisl, sit amet cursus ligula egestas feugiat.
      Phasellus eget tellus urna. Fusce aliquet sollicitudin tortor. Maecenas dignissim est sed massa commodo fermentum.
      Donec accumsan ante vitae sem egestas venenatis. Mauris ultrices, mauris ac tincidunt dictum, lorem nisl
      sollicitudin justo, ut ullamcorper velit lectus quis massa. Mauris id nisl nec augue euismod facilisis. Curabitur
      accumsan suscipit venenatis. Nullam luctus venenatis magna non accumsan. Praesent quis luctus tortor. Pellentesque
      quam orci, tristique at dictum at, viverra vitae lorem. Proin tortor nisi, ullamcorper et urna vel, faucibus
      pulvinar erat. Etiam sed arcu magna. Integer vitae accumsan justo, in ornare odio. Nullam scelerisque lobortis
      mauris in blandit. Etiam malesuada justo egestas, lobortis nibh efficitur, commodo ligula. Donec sagittis a magna
      ut fringilla. Curabitur euismod elit orci, nec aliquet odio scelerisque nec. Vivamus a auctor dolor. Sed et
      rhoncus diam, eget condimentum arcu. Ut efficitur pharetra nisl ut aliquam. Aenean nulla massa, tempus ut nisi at,
      bibendum ultrices dolor. Fusce nec libero risus. Morbi at ante vitae lectus sollicitudin semper. In et hendrerit
      nisl. Suspendisse potenti. Cras odio orci, elementum non quam sit amet, finibus viverra erat. Donec fermentum
      rhoncus dui, sit amet tristique nulla placerat eget. Praesent ultricies lorem semper magna iaculis facilisis.
      Pellentesque sed tincidunt sapien. Nulla vel sapien lectus. Donec sit amet lacinia diam. Orci varius natoque
      penatibus et magnis dis parturient montes, nascetur ridiculus mus. Etiam pretium turpis nunc, nec hendrerit neque
      bibendum vitae. Nulla malesuada, arcu nec dictum tempus, ipsum magna rutrum ex, ut elementum tortor tortor ut
      tellus. Proin porta, felis ut elementum consequat, enim turpis gravida felis, vel blandit urna libero vel elit. In
      ante quam, ornare sit amet orci id, lobortis interdum leo. Cras lectus mi, iaculis in ultricies a, pretium sit
      amet risus. In interdum mi ac rutrum imperdiet. Pellentesque vel mauris erat. Fusce faucibus in arcu in dictum.
      Nullam sodales placerat justo, nec suscipit felis interdum non.
    </p>
  </section>
  <!-- <section class="h-screen grid place-content-center bg-tertiary">
    <p class="reveal-type">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores</p>
  </section>
  <section class="h-screen grid place-content-center bg-secondary text-black">
    <p class="reveal-type">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam animi, asperiores</p>
  </section> -->
  <!-- <section class="h-screen"></section> -->
</template>

<script lang="ts" setup>
import gsap from 'gsap';
import SplitType from 'split-type';

definePageMeta({
  title: 'Terzo testo',
});

useHead({
  bodyAttrs: {
    class: `overflow-hidden`,
  },
  title: 'Terzo testo',
});

onMounted(() => {
  animations();
});

const animations = () => {
  const splitTypes = document.querySelectorAll('.reveal-type');
  splitTypes.forEach((char, i) => {
    const text = new SplitType(char as HTMLElement, { types: 'lines' });
    if (text.lines === null) return;
    text.lines.forEach(line => {
      gsap.fromTo(
        line,
        {
          opacity: 0.2,
        },
        {
          opacity: 1,
          stagger: 0.02,
          scrollTrigger: {
            trigger: line,
            start: 'top 52.5%',
            end: 'bottom 47.5%',
            toggleActions: 'play reverse play reverse',
          },
        }
      );
    });
  });
};
</script>

<style scoped>
section {
  padding: 0 clamp(4rem, 12vw, 20rem);
}

section p {
  font-size: clamp(0.75rem, 5vw, 1.5rem);
}
</style>
