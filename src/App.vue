<script setup>

</script>

<template>
  <div>
    <div id="nav">
      <router-link to="/">Home</router-link> 
      <router-link to="/brazil">Brazil</router-link>
      <router-link to="/hawaii">Hawaii</router-link>
      <router-link to="/jamaica">Jamaica</router-link>
      <router-link to="/panama">Panama</router-link>
    </div>
    <div class="container">
      <router-view />
    </div>
  </div>

</template>

<!-- <style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style> -->
