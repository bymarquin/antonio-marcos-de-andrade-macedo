<script setup>
import hero from '@/assets/carro-hero.png'
import AppLink from '@/components/AppLink.vue'
import estrada from '@/assets/carro-estrada.png'
import recarga from '@/assets/feat-recarga.png'
import painel from '@/assets/feat-painel.png'
import pontos from '@/assets/feat-pontos.png'
import design from '@/assets/feat-design.png'
import detalhes from '@/assets/carro-detalhes.png'
import ponto from '@/assets/ponto.svg'
import pontoLegenda from '@/assets/ponto-legenda.svg'
import chevron from '@/assets/chevron.svg'

const lorem =
  "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard."

const stats = [
  ['520 KM', 'com 1 carga'],
  ['2.800 RPM', 'de torque'],
  ['10 anos', 'garantia'],
]

const features = [
  { title: 'recarga rápida', img: recarga },
  { title: 'painel de instrumentos', img: painel },
  { title: 'pontos de recarga', img: pontos },
  { title: 'design premiado', img: design },
]

// x/y em px do design (imagem 1074x604); renderizados em %
const hotspots = [
  { k: 'A', x: 167, y: 185, label: 'Retrovisores inteligentes' },
  { k: 'B', x: 116, y: 399, label: 'Rodas de liga leve' },
  { k: 'C', x: 325, y: 235, label: 'Reconhecimento de digital' },
  { k: 'D', x: 585, y: 212, label: 'Sensor de proximidade' },
  { k: 'E', x: 705, y: 81, label: 'Antena 5G' },
  { k: 'F', x: 687, y: 351, label: 'Design sofisticado' },
  { k: 'G', x: 842, y: 203, label: 'Abertura automática' },
  { k: 'H', x: 999, y: 416, label: 'Câmera de estacionamento' },
]

const faq = [
  'Qual é a autonomia real da bateria em diferentes condições de condução?',
  'Quanto tempo o carro leva para carregar em tomadas residenciais e em carregadores rápidos?',
  'Como funciona a infraestrutura de recarga para viagens de longa distância?',
  'Qual é o tempo de garantia da bateria e qual a sua vida útil estimada?',
  'Quais são as principais economias em manutenção e impostos comparado a um carro a combustão?',
]
</script>

<template>
  <section class="flex flex-col items-center px-[var(--pad)] text-center">
    <img :src="hero" alt="Vinci Model V2" class="-mt-[23px] w-[947px] max-w-full" />
    <h1
      class="-mt-[20px] mb-[14px] text-[clamp(36px,6vw,72px)] leading-none font-normal tablet:mt-[8px]"
    >
      VINCI MODEL V2
    </h1>
    <p class="mt-0 w-[911px] max-w-full font-body text-[20px] leading-[36px] text-muted">
      Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has
      been the industry's standard dummy text ever.
    </p>
    <div class="mt-[27px] flex flex-wrap justify-center gap-[17px]">
      <AppLink
        to="/"
        class="grid h-[52px] w-[273px] max-w-full place-items-center rounded-[4px] border border-brand bg-brand text-[20px] font-medium text-white uppercase"
        >Modelos</AppLink
      >
      <a
        href="#"
        class="grid h-[52px] w-[273px] max-w-full place-items-center rounded-[4px] border border-black text-[20px] font-medium uppercase"
        >Test Drive</a
      >
    </div>
  </section>

  <section class="mt-[69px] px-[var(--pad)] text-center font-light uppercase">
    <h2 class="mb-[37px] text-[24px] font-light text-muted mobile:text-[18px]">
      tecnologia aliada ao futuro
    </h2>
    <dl
      class="flex justify-center text-left mobile:flex-col mobile:items-center mobile:text-center"
    >
      <div
        v-for="([valor, legenda], index) in stats"
        :key="valor"
        class="pr-[clamp(20px,4.5vw,65px)] last:pr-0 mobile:py-[20px] mobile:pr-0 mobile:last:pl-0"
        :class="
          index > 0
            ? 'border-l border-[#d3d0d0] pl-[clamp(20px,4vw,58px)] mobile:border-t mobile:border-l-0'
            : ''
        "
      >
        <dt class="text-[clamp(36px,5vw,72px)] leading-none">{{ valor }}</dt>
        <dd class="mt-[8px] text-[24px]">{{ legenda }}</dd>
      </div>
    </dl>
  </section>

  <div class="mx-[var(--pad)] mt-[clamp(40px,5.6vw,81px)]">
    <img
      :src="estrada"
      alt=""
      class="h-[clamp(200px,36vw,520px)] w-full rounded-[12px] object-cover"
    />
  </div>

  <section
    class="mt-[32px] grid grid-cols-[repeat(4,1fr)] tablet:grid-cols-[1fr_1fr] mobile:grid-cols-[1fr]"
  >
    <article v-for="(f, index) in features" :key="f.title">
      <div
        class="min-h-[191px] px-[26px] pt-[37px] pb-[24px] mobile:border-l-0"
        :class="
          index === 0
            ? ''
            : index % 2 === 0
              ? 'border-l border-[#e8e8e8] tablet:border-l-0'
              : 'border-l border-[#e8e8e8]'
        "
      >
        <h3 class="mb-[16px] text-[26px] leading-none font-normal uppercase">{{ f.title }}</h3>
        <p class="max-w-[319px] font-body text-[16px] leading-[28px] text-[#979797]">{{ lorem }}</p>
      </div>
      <img :src="f.img" alt="" class="h-[272px] w-full object-cover" />
    </article>
  </section>

  <section class="mx-auto mt-[55px] w-[min(1360px,calc(100%-2*var(--pad)))]">
    <div
      class="grid min-h-[149px] grid-cols-[1fr_229px_228px] gap-x-[36px] tablet:min-h-0 tablet:grid-cols-[1fr_1fr] tablet:gap-y-[24px] mobile:grid-cols-[1fr]"
    >
      <div class="tablet:col-span-full">
        <h2 class="text-[42px] leading-none font-normal">VINCI MODEL V2</h2>
        <p
          class="mt-[24px] w-[379px] font-body text-[16px] leading-[32px] text-muted tablet:w-auto tablet:max-w-[379px]"
        >
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has
          been the industry's standard dummy text ever.
        </p>
      </div>
      <ul
        v-for="col in [hotspots.slice(0, 4), hotspots.slice(4)]"
        :key="col[0].k"
        class="flex list-none flex-col gap-[17px] p-0 text-[16px] text-muted uppercase"
      >
        <li
          v-for="h in col"
          :key="h.k"
          class="flex items-center gap-[9px] whitespace-nowrap mobile:whitespace-normal"
        >
          <span
            class="relative isolate grid h-[18px] w-[18px] flex-none place-items-center font-body text-[12px] text-white"
          >
            <img :src="pontoLegenda" alt="" class="absolute inset-0 -z-[1]" />{{ h.k }}
          </span>
          {{ h.label }}
        </li>
      </ul>
    </div>
    <div class="relative mx-auto mt-[1px] aspect-[1074/604] w-[min(1074px,100%)]">
      <img :src="detalhes" alt="Vinci Model V2 em detalhes" class="h-full w-full object-cover" />
      <span
        v-for="h in hotspots"
        :key="h.k"
        class="absolute isolate grid h-[18px] w-[18px] flex-none place-items-center font-body text-[12px] text-white"
        :style="{ left: (h.x / 1074) * 100 + '%', top: (h.y / 604) * 100 + '%' }"
      >
        <img :src="ponto" alt="" class="absolute inset-0 -z-[1]" />{{ h.k }}
      </span>
    </div>
  </section>

  <section
    class="mt-[26px] -mb-[13px] border-b border-[#bcbcbc] px-[max(var(--pad),calc((100%-1064px)/2))] pb-[86px] text-center"
  >
    <h2 class="text-[42px] leading-none font-normal mobile:text-[32px]">FAQ</h2>
    <p class="mt-[18px] text-[22px] tracking-[2.2px] text-[#979797] mobile:text-[16px]">
      PERGUNTAS FREQUENTES
    </p>
    <ul class="mt-[45px] flex list-none flex-col gap-[53px] p-0 text-left mobile:gap-[28px]">
      <li
        v-for="q in faq"
        :key="q"
        class="flex items-center justify-between gap-[24px] text-[clamp(15px,1.8vw,26px)] leading-[1.25] text-ink uppercase"
      >
        <span>{{ q }}</span>
        <img :src="chevron" alt="" class="flex-none rotate-180" />
      </li>
    </ul>
  </section>
</template>
