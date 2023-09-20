<template>
  <div class="relative isolate z-50 shadow">
    <div class="bg-white py-5">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <button
          type="button"
          class="inline-flex items-center gap-x-1 text-sm font-semibold leading-6 text-gray-900"
          :aria-expanded="mobileMenuIsOpen"
          @click="$emit('toggle-mobile-menu')">
          Effetti
          <svg class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
            <path
              fill-rule="evenodd"
              d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
              clip-rule="evenodd" />
          </svg>
          <small>{{ $router.currentRoute.value?.meta?.title }}</small>
        </button>
      </div>
    </div>
    <div
      class="absolute inset-x-0 top-0 -z-10 bg-white pt-16 shadow-lg ring-1 ring-gray-900/5 transition ease-out duration-200"
      :class="!mobileMenuIsOpen ? 'opacity-0 -translate-y-1' : 'opacity-100 translate-y-0'">
      <div class="mx-auto grid max-w-7xl grid-cols-1 gap-x-8 gap-y-10 px-6 py-10 lg:grid-cols-2 lg:px-8">
        <div class="grid grid-cols-2 gap-x-6 sm:gap-x-8">
          <div>
            <NuxtLink
              to="/"
              class="flex gap-x-4 py-2 text-sm -mt-12 mb-2 font-semibold leading-6 text-gray-900"
              @click="$emit('toggle-mobile-menu')">
              Home
            </NuxtLink>
            <h3 class="text-sm font-medium leading-6 text-gray-500">Orizzontali</h3>
            <div class="mt-6 flow-root">
              <div class="-my-2">
                <NuxtLink
                  to="/orizzontali/primo"
                  class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"
                  @click="$emit('toggle-mobile-menu')">
                  Primo
                </NuxtLink>
                <NuxtLink
                  to="/orizzontali/secondo"
                  class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"
                  @click="$emit('toggle-mobile-menu')">
                  Secondo
                </NuxtLink>
              </div>
            </div>
          </div>
          <div>
            <h3 class="text-sm font-medium leading-6 text-gray-500">Testi</h3>
            <div class="mt-6 flow-root">
              <div class="-my-2">
                <NuxtLink
                  to="/testi/primo"
                  class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"
                  @click="$emit('toggle-mobile-menu')">
                  Primo
                </NuxtLink>

                <NuxtLink
                  to="/testi/secondo"
                  class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"
                  @click="$emit('toggle-mobile-menu')">
                  Secondo
                </NuxtLink>
                <NuxtLink
                  to="/testi/terzo"
                  class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"
                  @click="$emit('toggle-mobile-menu')">
                  Terzo
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>

        <div class="grid grid-cols-2 gap-x-6 sm:gap-x-8">
          <div>
            <h3 class="text-sm font-medium leading-6 text-gray-500">Gallery</h3>
            <div class="mt-6 flow-root">
              <div class="-my-2">
                <NuxtLink
                  to="/gallerie/primo"
                  class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"
                  @click="$emit('toggle-mobile-menu')">
                  Primo
                </NuxtLink>
              </div>
            </div>
          </div>
          <div>
            <!-- <h3 class="text-sm font-medium leading-6 text-gray-500">Resources</h3>
            <div class="mt-6 flow-root">
              <div class="-my-2">
                <a href="#" class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"> Community </a>
                <a href="#" class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"> Partners </a>
                <a href="#" class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"> Guides </a>
                <a href="#" class="flex gap-x-4 py-2 text-sm font-semibold leading-6 text-gray-900"> Webinars </a>
              </div>
            </div> -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
const props = defineProps({
  mobileMenuIsOpen: { type: Boolean, required: true },
});
</script>
