<script setup>
import LandingPage from "@/views/LandingPage.vue";
import ContentSide from "@/views/ContentSide.vue";
import {useMouse} from "@vueuse/core";
import {ref} from "vue";

const isLightTheme = ref(true)
const { x, y } = useMouse()

function toggleTheme() {
  isLightTheme.value = !isLightTheme.value
}

</script>

<template>
  <div class="main-container px-md-0 px-4 py-md-0 py-4" :class="{'dark-theme' : !isLightTheme}" style="color: var(--text-color)">
    <div class="d-flex justify-content-md-start justify-content-end m-2 m-md-0">
      <iconify-icon v-if="!isLightTheme" icon="ri:moon-line" width="1.7rem" class="moon-icon" style="color: #d4d4d4" @click="toggleTheme"></iconify-icon>
      <iconify-icon v-else icon="ph:sun-bold" width="1.7rem" class="sun-icon" @click="toggleTheme"></iconify-icon>
    </div>
    <div class="d-md-flex px-xxl-0 px-3">
      <div class="index-left">
        <landing-page></landing-page>
      </div>
      <div class="index-right">
        <content-side></content-side>
      </div>
    </div>

    <div v-if="!isLightTheme" class="spotlight" :style="{left: `${x}px`, top: `${y}px`}"></div>
  </div>
</template>

<style scoped>

</style>