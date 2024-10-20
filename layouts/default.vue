<script setup>
import Sidebar from '~/compornents/Sidebar.vue'
</script>

<template>
<div class="wrapper">
  <Sidebar />
  <div class="contents">
    <slot />
  </div>
</div>
</template>

<style scoped>
.wrapper {
  width: 100%;
  height: 100vh;
  display: grid;
  grid-template-columns: 300px auto;
  gap: 0 10px;
}
</style>