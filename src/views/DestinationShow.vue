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
    props: {
      id: {
        type: String,
        required: true
      }
    },
    computed: {
      // destinationID() {
      //   return parseInt( this.$route.params.id )
      // },

      destination() {
      // find the destination with the same id as the route parameter
      return sourceData.destinations.find( destination => destination.id ==parseInt( this.id) )
      }
    },
    
  }
</script> -->

<script setup>
// composition API
import { computed } from 'vue'
import sourceData from '@/data.json'

const props = defineProps({
  id: {
    type: String,
    required: true
  }
})


const destination = computed(() => {
  return sourceData.destinations.find(destination => destination.id == parseInt(props.id))
})


</script>




<!-- 
 <script setup>
 // composition API
import { computed } from 'vue'
import sourceData from '@/data.json'

// Define props
const props = defineProps({
  id: {
    type: String,
    required: true
  }
})

// Find the destination with the same id as the prop id
const destination = computed(() => {
  return sourceData.destinations.find(destination => destination.id === parseInt(props.id))
})
</script> -->
