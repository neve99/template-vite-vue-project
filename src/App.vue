<script>
  import TheNavigation from '@/components/TheNavigation.vue'
  export default{
    components: {
      TheNavigation
    }
  }
</script>

<template>
  <TheNavigation />
  <div>
    
    <div class="container">
      <router-view />
    </div>
  </div>

</template>


