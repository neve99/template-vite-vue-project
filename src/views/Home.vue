<template>
  <div class="home">
    <h1>All destinations</h1>
    <router-link
      v-for="destination in destinations"
      :key="destination.id"
      :to="destination.slug"
    >
      <h2>{{ destination.name }}</h2>
      <img :src="`/images/${destination.image}`" alt="">
    </router-link>
  </div>
</template>

<script>
import sourceData from '@/data.json'
export default {

  data() {
    return {
      destinations: sourceData.destinations
    }
  }
}
</script>