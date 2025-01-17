<template>
  <div id="nav">
    <router-link to="/" id="logo">RandomTravel Agency</router-link>
      
    <router-link to="/">Home</router-link>
      <router-link
      v-for="destination in destinations"
      :key="destination.id"
      :to="{ name: 'destination.show', params: { id: destination.id, slug: destination.slug} }"
    >
    <!-- jump tp destination.show page for dynamic routing -->
    {{ destination.name }}

    </router-link>
    </div>
</template>

<script setup>
import sourceData from '@/data.json'
const destinations = sourceData.destinations
</script>