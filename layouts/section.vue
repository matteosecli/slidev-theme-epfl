<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  image: {
    type: String,
  },
  class: {
    type: String,
  },
  color: {
    type: String,
    default: '--epfl-rouge',
  },
})
</script>

<template>
  <div class="grid grid-cols-2 w-full h-full auto-rows-fr">
    <div class="h-full ml-[6rem]" :style="{ backgroundImage: `url(${props.image})`, backgroundPosition: 'center', backgroundSize: 'cover' }"  />
    <div class="w-full h-full slidev-layout section" :style="{ backgroundColor: `var(${props.color})`, color: `var(--epfl-main-color-light)` }" >
      <slot />
    </div>
  </div>
</template>