<script setup>
import AppLogo from './AppLogo.vue'

const cols = {
  Sobre: ['A Marca', 'História', 'Qualidade', 'Onde estamos', 'Investidores'],
  Contato: ['Fale Conosco', 'Atendimento', 'SAC'],
  SAC: ['Canais Oficiais', 'Redes Sociais', 'Suporte'],
}
</script>

<template>
  <footer
    class="grid min-h-[311px] grid-cols-[1fr_254px_249px_auto] px-[var(--pad)] whitespace-nowrap compact:min-h-0 compact:grid-cols-[repeat(3,auto)] compact:justify-between compact:gap-x-[24px] compact:gap-y-[40px] compact:whitespace-normal mobile:grid-cols-[1fr_1fr]"
  >
    <div class="flex flex-col justify-between compact:contents">
      <AppLogo class="compact:col-span-full" />
      <p
        class="text-[16px] leading-[24px] tracking-[6.4px] text-muted uppercase compact:order-2 compact:col-span-full mobile:tracking-[3px]"
      >
        ©Copyright 2026.<br />Todos os Direitos Reservados.
      </p>
    </div>
    <section v-for="(links, title) in cols" :key="title" class="flex flex-col compact:order-1">
      <h3
        class="mb-[26px] text-[24px] leading-none font-normal tracking-[4.8px] uppercase mobile:mb-[12px] mobile:text-[20px] mobile:tracking-[3px]"
      >
        {{ title }}
      </h3>
      <a
        v-for="l in links"
        :key="l"
        href="#"
        class="text-[20px] leading-[42px] tracking-[4px] text-muted mobile:text-[16px] mobile:leading-[34px] mobile:tracking-[2px]"
        >{{ l }}</a
      >
    </section>
  </footer>
</template>
