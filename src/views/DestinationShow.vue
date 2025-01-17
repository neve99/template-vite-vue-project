<template>
  <div>
    <h2>{{ destination.name }}</h2>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name">
      <p>{{ destination.description }}</p>
    </div>
  </div>
</template>

<!-- <script>
  import sourceData from '@/data.json'

  export default {
    computed: {
      destinationID() {
        return parseInt( this.$route.params.id )
      },

      destination() {
      // find the destination with the same id as the route parameter
      return sourceData.destinations.find( destination => destination.id === this.destinationID )
      }
    },
    
  }
</script> -->

<script setup>
// composition API
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import sourceData from '@/data.json'

const route = useRoute()
const destinationID = computed(() => parseInt(route.params.id))
// find the destination with the same id as the route parameter
const destination = computed(() => sourceData.destinations.find(destination => destination.id === destinationID.value))
</script>