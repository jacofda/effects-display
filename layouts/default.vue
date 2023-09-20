<template>
  <div class="">
    <LayoutTheHeader :mobile-menu-is-open="mobileMenuIsOpen" @toggle-mobile-menu="toggleMobileMenu" />
    <slot />
  </div>
</template>
<script setup lang="ts">
import { useConfig } from '../composables/useConfig';

const config = useConfig();

const mobileMenuIsOpen = ref(false);

const toggleMobileMenu = () => {
  mobileMenuIsOpen.value = !mobileMenuIsOpen.value;
};
</script>
