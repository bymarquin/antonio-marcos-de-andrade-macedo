<script setup>
import seta from '@/assets/seta.svg'

const items = ['Agende um test drive', 'Veja ofertas', 'Encontre uma loja']
</script>

<template>
  <nav class="px-[var(--pad)]">
    <a
      v-for="i in items"
      :key="i"
      href="#"
      class="flex items-center justify-between gap-[16px] py-[3px] text-[clamp(24px,5vw,72px)] leading-none uppercase"
    >
      <span>{{ i }}</span>
      <span class="grid h-[35px] w-[23px] flex-none place-items-center">
        <img :src="seta" alt="" class="h-[23px] w-[35px] max-w-none rotate-90" />
      </span>
    </a>
  </nav>
</template>
