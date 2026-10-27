<script setup>
import branco from '@/assets/carro-hero.png'
import vermelho from '@/assets/menu-vermelho.png'
import preto from '@/assets/menu-preto.png'
import verde from '@/assets/menu-verde.png'
import AppLink from './AppLink.vue'

const models = [
  { name: 'Modelo V1', img: branco },
  { name: 'Modelo V2', img: vermelho, cover: true, to: '/carro' },
  { name: 'Modelo V3', img: preto, cover: true },
  { name: 'Modelo V1', img: verde, cover: true },
  { name: 'Modelo V1', img: branco },
  { name: 'Modelo V1', img: branco },
]
const links = ['Ofertas', 'Test Drive', 'Lojas', 'Serviços', 'SAC', 'Privacidade']
</script>

<template>
  <div
    class="absolute top-full left-0 grid h-[524px] w-full grid-cols-[calc(66.67%+16px)_1fr] border-t border-[#d8d8d8] bg-white shadow-[0_7px_27.4px_-9px_rgba(0,0,0,0.13)] tablet:hidden"
  >
    <ul
      class="mt-[25px] ml-[var(--pad)] grid list-none grid-cols-[repeat(3,minmax(0,296px))] content-start gap-x-[8px] gap-y-[26px] p-0"
    >
      <li v-for="(m, i) in models" :key="i" class="flex flex-col items-center">
        <img
          :src="m.img"
          alt=""
          :class="
            m.cover
              ? 'my-[11px] h-[122px] w-[min(250px,100%)] object-cover'
              : 'h-[144px] w-full object-contain'
          "
        />
        <strong
          class="mt-[4px] text-[18px] leading-[32px] font-medium tracking-[1.8px] text-ink uppercase"
          >{{ m.name }}</strong
        >
        <div class="flex gap-[27px] text-[16px] leading-[20px] text-ink">
          <AppLink :to="m.to">Ver mais</AppLink>
          <a href="#">Comprar</a>
        </div>
      </li>
    </ul>
    <div class="mt-[33px] h-[453px] border-l border-[#d8d8d8] pl-[21px]">
      <h3
        class="h-[37px] w-[min(275px,100%)] border-b border-[#d8d8d8] pt-[6px] text-[14px] leading-[24px] font-medium tracking-[5.6px] text-[#979797] uppercase"
      >
        Navegue
      </h3>
      <a
        v-for="(l, i) in links"
        :key="l"
        href="#"
        class="ml-[30px] block text-[14px] leading-[42px] font-medium tracking-[2.8px] uppercase"
        :class="[i === 0 ? 'mt-[13px]' : '', l === 'Test Drive' ? 'text-brand' : 'text-black']"
        >{{ l }}</a
      >
    </div>
  </div>
</template>
