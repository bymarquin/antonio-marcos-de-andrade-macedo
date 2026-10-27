<script setup>
import hero from '@/assets/hero.png'
import AppLink from './AppLink.vue'
</script>

<template>
  <section
    class="relative flex h-[637px] items-end text-white before:absolute before:inset-y-0 before:left-0 before:w-[78%] before:bg-[linear-gradient(to_left,transparent,rgba(0,0,0,0.48))] before:content-[''] tablet:before:w-full tablet:before:bg-[rgba(0,0,0,0.45)] tablet:before:bg-none mobile:h-[540px]"
  >
    <img :src="hero" alt="" class="absolute inset-0 h-full w-full object-cover object-[50%_96%]" />
    <div class="relative w-full px-[var(--pad)] pb-[74px] mobile:pb-[40px]">
      <h1 class="text-[clamp(36px,6vw,72px)] leading-none font-normal">VINCI MODEL V3</h1>
      <p
        class="mb-[33px] w-[706px] max-w-full font-body text-[20px] leading-[36px] mobile:mb-[24px] mobile:text-[16px] mobile:leading-[28px]"
      >
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has
        been the industry's standard dummy text ever.
      </p>
      <div class="flex flex-wrap gap-[17px] mobile:flex-col mobile:gap-[12px]">
        <AppLink
          to="/#modelos"
          class="grid h-[52px] w-[273px] max-w-full place-items-center rounded-[4px] border border-brand bg-brand text-[20px] font-medium uppercase mobile:w-full"
          >Modelos</AppLink
        >
        <a
          href="#"
          class="grid h-[52px] w-[273px] max-w-full place-items-center rounded-[4px] border border-white text-[20px] font-medium uppercase mobile:w-full"
          >Test Drive</a
        >
      </div>
    </div>
  </section>
</template>
