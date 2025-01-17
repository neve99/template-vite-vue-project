<script setup>
import TheNavigation from '@/components/TheNavigation.vue'
</script>

<template>
  <div>
    <TheNavigation />
    <div class="container">
      <router-view :key="$route.path" />
    </div>
  </div>

</template>


