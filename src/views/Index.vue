<script setup>

import LandingPage from "@/views/LandingPage.vue";
import ContentSide from "@/views/ContentSide.vue";
</script>

<template>
  <div>
    <iconify-icon icon="ph:sun-bold" width="1.7rem" class="sun-icon"></iconify-icon>
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