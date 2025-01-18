<script setup>
import TheNavigation from '@/components/TheNavigation.vue'
</script>

<template>
  <div>
    <TheNavigation />
    <div class="container">
      <router-view v-slot="{Component}" >
        <transition name="fade" mode="out-in" >
          <component :is="Component" :key="$route.path"/>
        </transition>
      </router-view>
    </div>
  </div>

</template>

<style lang="css">
.fade-enter-active, .fade-leave-active {
  transition: opacity .3s;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;

}
</style>