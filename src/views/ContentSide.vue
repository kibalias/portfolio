<script setup>
import data from '@/assets/data.json'

const timeline_data = data
</script>

<template>
<div>
  <div v-for="(value, key, index) in timeline_data">
    <div>
      <div class="title mt-4">
        {{key.toUpperCase()}}
      </div>
      <div class="content-wrapper">
        <div v-for="val in value" class="content-container">
          <div class="content-header">
            {{key === 'education' ? val.school : val. job_title}}
          </div>
          <div v-if="key === 'education'" class="content-body">
            <h6 class="fw-semibold mb-0">{{val.course}}</h6>
            <p class="sub-info mb-0">{{val.place}}</p>
          </div>
          <div v-if="key === 'experience'" class="content-body">
            <h6 class="fw-semibold mb-0">{{val.company}}</h6>
            <p class="sub-info mb-0">{{val.year}} </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<style scoped>

</style>