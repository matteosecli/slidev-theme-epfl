<template>
  <!-- EPFL Logo | Right now LightOrDark is the same, but we may want to change that at some point -->
  <LightOrDark>
    <template #light>
      <img 
        src="./assets/epfl-logo-rouge.svg"
        alt="EPFL logo"
        class="absolute top-[0.5rem] left-[0.5rem] w-[5rem] epfl-persistent"
        v-if="$slidev.nav.currentLayout !== 'image' && $slidev.nav.currentLayout !== 'cover'"
      />
      <img 
        src="./assets/epfl-logo-rouge.svg"
        alt="EPFL logo"
        class="absolute top-0 left-0 w-[9rem] epfl-persistent"
        v-if="$slidev.nav.currentLayout == 'cover'"
      />
    </template>
    <template #dark>
      <img 
        src="./assets/epfl-logo-rouge.svg"
        alt="EPFL logo"
        class="absolute top-[0.5rem] left-[0.5rem] w-[5rem] epfl-persistent"
        v-if="$slidev.nav.currentLayout !== 'image' && $slidev.nav.currentLayout !== 'cover'"
      />
      <img 
        src="./assets/epfl-logo-rouge.svg"
        alt="EPFL logo"
        class="absolute top-0 left-0 w-[9rem] epfl-persistent"
        v-if="$slidev.nav.currentLayout == 'cover'"
      />
    </template>
  </LightOrDark>
  <!-- Left bar -->
  <div
    class="absolute bottom-5.5 left-[2.6875rem] text-[10px] flex items-center writing-mode-vertical-lr rotate-180 epfl-header leading-tight epfl-persistent"
    v-if="$slidev.nav.currentLayout !== 'image' && $slidev.nav.currentLayout !== 'cover'"
  >
    <div class="w-[6.5px] h-[5.57px] bg-current mb-2 shrink-0"></div>
    {{ frontmatter.header || $slidev?.configs?.header || '' }}
  </div>
  <div
    class="absolute bottom-5.5 left-[0.5rem] text-[10px] flex items-top epfl-header leading-tight epfl-persistent"
    v-if="$slidev.nav.currentLayout == 'cover'"
  >
    <div class="w-[6.5px] h-[5.57px] bg-current mt-[2.8525px] shrink-0 mr-[0.5rem]"></div>
    <div class="font-medium">
      <div>École</div> <!-- text line is 13.53px including post, factor 1.2 -->
      <div>polytechnique</div>
      <div>fédérale</div>
      <div>de Lausanne</div>
    </div>
  </div>
  <!-- Right bar -->
  <div
    class="absolute right-[1.4375rem] top-0 text-[10px] flex justify-between items-end py-6 text-xs rotate-180 writing-mode-vertical-lr epfl-persistent"
    :class="$slidev.nav.currentLayout == 'section' ? 'epfl-footer-light' : 'epfl-footer'"
    v-if="$slidev.nav.currentLayout !== 'image' && $slidev.nav.currentLayout !== 'cover'"
  >
    <div class="mb-6">{{ frontmatter.footer || $slidev?.configs?.footer || '' }}</div>
    <div class="rotate-90 shrink-0" v-if="frontmatter.number || $slidev?.configs?.number">{{ nav.currentPage }}</div>
  </div>
</template>

<script setup>
const frontmatter = $slidev?.frontmatter || {}
const nav = $slidev.nav
</script>

<style scoped>
.writing-mode-vertical-lr {
  writing-mode: vertical-lr;
}
.epfl-header {
  color: var(--epfl-rouge);
}
.epfl-footer {
  color: var(--epfl-text-color);
}
.epfl-footer-light {
  color: var(--epfl-main-color-light);
}
</style>