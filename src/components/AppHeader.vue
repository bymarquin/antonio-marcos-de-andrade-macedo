<script setup>
import { ref } from 'vue'
import AppLogo from './AppLogo.vue'
import AppLink from './AppLink.vue'
import MegaMenu from './MegaMenu.vue'

const links = [['Home', '/'], ['Sobre'], ['Veículos', '/carro'], ['Serviços'], ['Test Drive']]
const open = ref(false) // megamenu de "Veículos" (desktop)
const menu = ref(false) // gaveta (tablet/celular)
const close = () => (open.value = menu.value = false)
</script>

<template>
  <header
    class="relative z-10 flex h-[80px] items-center justify-between bg-white px-[var(--pad)]"
    @mouseleave="open = false"
    @keydown.esc="close"
  >
    <AppLogo />
    <button
      class="hidden h-[40px] w-[40px] cursor-pointer border-0 bg-transparent p-0 tablet:block"
      :aria-expanded="menu"
      aria-label="Menu"
      @click="menu = !menu"
    >
      <span
        class="relative m-auto block h-[2px] w-[24px] transition-transform duration-200 ease-[ease] before:absolute before:-top-[8px] before:left-0 before:m-auto before:block before:h-[2px] before:w-[24px] before:bg-ink before:transition-transform before:duration-200 before:ease-[ease] before:content-[''] after:absolute after:top-[8px] after:left-0 after:m-auto after:block after:h-[2px] after:w-[24px] after:bg-ink after:transition-transform after:duration-200 after:ease-[ease] after:content-['']"
        :class="
          menu
            ? 'bg-transparent before:[transform:translateY(8px)_rotate(45deg)] after:[transform:translateY(-8px)_rotate(-45deg)]'
            : 'bg-ink'
        "
      />
    </button>
    <nav
      class="relative z-[11] flex gap-[clamp(20px,6.667vw,96px)] self-stretch text-[16px] text-ink uppercase tablet:absolute tablet:top-full tablet:right-0 tablet:left-0 tablet:flex-col tablet:gap-0 tablet:border-t tablet:border-[#d8d8d8] tablet:bg-white tablet:px-[var(--pad)] tablet:pt-[8px] tablet:pb-[16px] tablet:text-[18px] tablet:shadow-[0_7px_27.4px_-9px_rgba(0,0,0,0.13)]"
      :class="menu ? 'tablet:flex' : 'tablet:hidden'"
    >
      <AppLink
        v-for="[label, to] in links"
        :key="label"
        :to="to"
        class="relative flex items-center tablet:py-[14px]"
        :class="
          open && label === 'Veículos'
            ? `after:absolute after:right-0 after:-bottom-[2px] after:left-0 after:h-[2px] after:bg-ink after:content-[''] tablet:after:hidden`
            : ''
        "
        @mouseenter="open = label === 'Veículos'"
        @focus="open = label === 'Veículos'"
        @click="close"
      >
        {{ label }}
      </AppLink>
    </nav>
    <MegaMenu v-if="open" @click="open = false" />
  </header>
</template>
