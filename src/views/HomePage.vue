<script setup>
import AppHero from '@/components/AppHero.vue'
import ModelCard from '@/components/ModelCard.vue'
import AppMenu from '@/components/AppMenu.vue'
import v1 from '@/assets/v1.png'
import v2 from '@/assets/v2.png'
import estrada from '@/assets/banner-estrada.png'
import final from '@/assets/banner-final.png'

const specs = [
  ['Potência;', '300 cavalos'],
  ['Autonomia:', '500km por carga'],
  ['Peso:', '1.500 kg'],
  ['Tecnologia:', 'GPS e Smartink'],
]
const description = 'A SUV mais robusta da categoria'
const models = [
  { model: 'V2', image: v2, to: '/carro' },
  { model: 'V1', image: v1 },
]
</script>

<template>
  <AppHero />
  <section
    id="modelos"
    class="grid grid-cols-[1fr_1fr] gap-x-[97px] px-[var(--pad)] py-[var(--gap)] stacked:grid-cols-[1fr] stacked:gap-y-[56px]"
  >
    <ModelCard
      v-for="m in models"
      :key="m.model"
      v-bind="m"
      :specs="specs"
      :description="description"
    />
  </section>
  <div class="h-[clamp(240px,41.2vw,593px)]">
    <img :src="estrada" alt="" class="h-full w-full object-cover" />
  </div>
  <div class="py-[calc(var(--gap)-min(20px,1.4vw))]"><AppMenu /></div>
  <div class="h-[clamp(240px,41.2vw,593px)]">
    <img :src="final" alt="" class="h-full w-full object-cover object-[50%_75%]" />
  </div>
</template>
