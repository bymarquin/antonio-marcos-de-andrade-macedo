<script setup>
import AppLink from './AppLink.vue'

defineProps({
  model: String,
  image: String,
  specs: Array, // [[rótulo, valor], ...]
  description: String,
  to: String,
})
</script>

<template>
  <article class="flex flex-col">
    <header
      class="relative z-[1] flex h-[80px] justify-between mobile:h-auto mobile:flex-wrap mobile:gap-[16px]"
    >
      <h2 class="text-[24px] leading-[1.2] font-normal tracking-[9.6px] mobile:tracking-[6px]">
        VINCI<br />MODEL {{ model }}
      </h2>
      <dl
        class="grid grid-cols-[auto_auto] content-start gap-x-[32px] text-[18px] leading-[24px] tracking-[1.8px]"
      >
        <template v-for="[label, value] in specs" :key="label">
          <dt>{{ label }}</dt>
          <dd class="text-[#979797]">{{ value }}</dd>
        </template>
      </dl>
    </header>
    <img
      :src="image"
      :alt="`Vinci Model ${model}`"
      class="mx-auto -mt-[16px] h-[clamp(220px,55vw,425px)] w-[90%] object-contain mobile:mt-[8px] mobile:w-full"
    />
    <footer
      class="-mt-[4px] -mb-[7px] flex justify-between text-[20px] leading-none tracking-[2px] text-[#685757] mobile:flex-wrap mobile:gap-x-[16px] mobile:gap-y-[8px] mobile:text-[16px] mobile:tracking-[1px]"
    >
      <span>{{ description }}</span>
      <AppLink :to="to" class="text-ink underline">CONHEÇA</AppLink>
    </footer>
  </article>
</template>
