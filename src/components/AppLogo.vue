<script setup>
import logo from '@/assets/logo.svg'
import AppLink from './AppLink.vue'
</script>

<template>
  <AppLink
    to="/"
    class="flex items-center gap-[28px] text-[41.659px] leading-none tracking-[16.66px] mobile:gap-[16px] mobile:text-[28px] mobile:tracking-[10px]"
  >
    <img :src="logo" alt="" width="40.5" height="34" class="mobile:h-auto mobile:w-[28px]" />
    <span>VINCI</span>
  </AppLink>
</template>
