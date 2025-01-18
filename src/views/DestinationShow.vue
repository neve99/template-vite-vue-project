<template>
  <section v-if="destination" class="destination">
    <h1>{{ destination.name }}</h1>
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name">
      <p>{{ destination.description }}</p>
    </div>
  </section>

  <section class="experiences"> 
    <h2>Top experiences in {{ destination.name }}</h2>
      <div class="cards">
        <router-link 
        v-for="experience in destination.experiences"
        :key="experience.slug"
        :to="{ name: 'experience.show', params: { id: destination.id, experienceSlug: experience.slug } }"
        >
          <ExperienceCard :experience="experience"/>
        </router-link>
      </div>
      <router-view />
  </section>
</template>

<script setup>
// composition API
import { computed } from 'vue'
import sourceData from '@/data.json'
import ExperienceCard from '@/components/ExperienceCard.vue';

const props = defineProps({
  id: {
    type: Number,
    required: true
  }
})


const destination = computed(() => {
  return sourceData.destinations.find(destination => destination.id === props.id)
})


</script>

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
