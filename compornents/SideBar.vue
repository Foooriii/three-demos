<script setup>
const links = [
  { path: '/', title: '関数チートシート', isPractice: false },
  { path: '/step1', title: 'step1：四角形回転（サイズ指定）', isPractice: true },
  { path: '/step2', title: 'step2：四角形回転（画面全体）', isPractice: false },
]
</script>

<template>
  <div class="sidebar">
    <h1>ThreeJS</h1>
    <ul>
      <li v-for="(link, i) in links" :key="i">
        <NuxtLink :to="link.path">{{ link.title }}</NuxtLink>
        <ul v-if="link.isPractice">
          <li><NuxtLink :to="`${link.path}/practice`">練習</NuxtLink></li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.sidebar {
  border-right: 1px solid gray;
  
  h1 { text-align: center; }
}

li {
  margin: 5px 0;
  a { color: #2367ff; }
}
</style>