<script setup lang="ts">
import { ref, onMounted, onUpdated } from 'vue'
// import { nextTick, computed } from 'vue'

const props = defineProps({
  title: {
    type: String,
    default: 'Title',
  },
  author: {
    type: String,
    default: 'Author Name',
  },
  affiliation: {
    type: String,
    //default: 'Affiliation',
  },
  date: {
    type: String,
    default: new Date().toLocaleDateString('en-US', {
      year: 'numeric',
      month: 'long',
      day: 'numeric',
    }),
  },
//   titleratio: {
//     type: String,
//     default: "7 / 6",
//   },
  image: String,
  imageLight: {
    type: String,
    default: '/public/backgrounds/epfl-aerial-view-1.jpg',
  },
  imageDark: {
    type: String,
    default: '/public/backgrounds/epfl-rlc-night-view-2.jpg',
  },
})

const titleBoxRef = ref<HTMLElement | null>(null)
const aspectRatio = ref(7 / 6)
// const ready = ref(false)
// const isReady = computed(() => ready.value)

// const fitTitleBox = async () => {
const fitTitleBox = () => {
  if (!titleBoxRef.value) return

  const box = titleBoxRef.value
  const maxWidth = 40 * 16 // 640px
  const maxHeight = 14.7 * 16 // 235.2px
  const maxAspect = maxWidth / maxHeight

  let ratio = 7
  const tryFit = () => {
    box.style.aspectRatio = `${ratio}/6`
    const tooTall = box.scrollHeight > box.offsetHeight
    const tooWide = box.scrollWidth > box.offsetWidth
    if ((tooTall || tooWide) && ratio / 6 <= maxAspect) {
      ratio++
      tryFit()
    } else {
      aspectRatio.value = ratio / 6
    }
    // ready.value = true
  }

  tryFit()

//   // Wait one tick to ensure DOM has updated
//   await nextTick()
//   ready.value = true
}

onMounted(() => {
  requestAnimationFrame(() => setTimeout(fitTitleBox, 50))
})

onUpdated(() => {
  requestAnimationFrame(() => setTimeout(fitTitleBox, 50))
})
</script>

<template>
  <div class="slidev-layout cover relative w-full h-full overflow-hidden">
    <!-- Background -->
    <LightOrDark>
      <template #light>
        <div
          class="absolute inset-0 w-full bg-cover bg-bottom ml-[9rem] mb-5.5"
          :style="{ backgroundImage: `url('${props.image || props.imageLight}')` }"
        />
      </template>
      <template #dark>
        <div
          class="absolute inset-0 w-full bg-cover bg-bottom ml-[9rem] mb-5.5"
          :style="{ backgroundImage: `url('${props.image || props.imageDark}')` }"
        />
      </template>
    </LightOrDark>

    <!-- Grid container -->
    <!-- v-show="isReady" -->
    <div
      class="absolute bottom-0 left-[8rem] grid gap-0 z-10"
      style="
        grid-template-columns: max-content 12.5rem 12.5rem;
        grid-template-rows: max-content 10.7rem 3.2rem;
        max-width: calc(40rem + 2 * 12.5rem);
      "
    >
      <!-- Red Title Box -->
      <div
        ref="titleBoxRef"
        class="bg-[var(--epfl-rouge)] text-[var(--epfl-main-color-light)] font-bold px-8 py-6 text-5xl leading-tight col-span-2 row-start-1 overflow-hidden"
        style="text-wrap: pretty; font-family: var(--epfl-heading-font); max-width: 40rem; max-height: 14.7rem;"
        :style="{
            // aspectRatio: `${props.titleratio}`,
            aspectRatio: aspectRatio.value,
            display: 'flex',
            alignItems: 'center',
            justifyContent: 'center',
            textAlign: 'left',
        }"
      >
        {{ $slidev.configs.title ?? props.title }}
      </div>

      <!-- Grey Author Box -->
      <div
        class="bg-[var(--epfl-main-color-dark)] text-[var(--epfl-main-color-light)] dark:bg-[var(--epfl-canard)] text-xl px-4 py-3 row-start-2 col-start-3 flex flex-col justify-center items-center text-center"
        style="font-family: var(--epfl-main-font); height: 10.7rem;"
      >
        <div class="font-bold">{{ $slidev.configs.author ?? props.author }}</div>
        <div class="font-normal">{{ props.affiliation }}</div>
      </div>

      <!-- White Date Box -->
      <div
        class="bg-[var(--epfl-main-color-light)] text-[var(--epfl-main-color-dark)] dark:bg-[var(--epfl-main-color-dark)] dark:text-[var(--epfl-main-color-light)] text-base font-bold px-4 py-2 row-start-3 col-start-2 flex justify-center items-center text-center"
        style="font-family: var(--epfl-main-font); height: 3.2rem;"
      >
        {{ props.date }}
      </div>
    </div>
  </div>
</template>