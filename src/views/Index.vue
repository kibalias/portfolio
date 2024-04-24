<script setup>
import LandingPage from "@/views/LandingPage.vue";
import ContentSide from "@/views/ContentSide.vue";
import {ref} from "vue";

const isLightTheme = ref(true)

function toggleTheme() {
  isLightTheme.value = !isLightTheme.value
  console.log(isLightTheme.value)
}
</script>

<template>
  <div class="main-container" :class="{'dark-theme' : !isLightTheme}" style="color: var(--text-color)">
    <iconify-icon v-if="!isLightTheme" icon="ri:moon-line" width="1.7rem" class="moon-icon" style="color: #d4d4d4" @click="toggleTheme"></iconify-icon>
    <iconify-icon v-else icon="ph:sun-bold" width="1.7rem" class="sun-icon" @click="toggleTheme"></iconify-icon>
    <div class="d-md-flex">
      <div class="index-left">
        <landing-page></landing-page>
      </div>
      <div class="index-right">
        <content-side></content-side>
      </div>

    </div>

  </div>
</template>

<style scoped>

</style>