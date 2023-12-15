<script setup lang="ts">
import Progress from './components/Progress.vue';
import { computed } from 'vue'

const num = computed(() => {
  const p = (($slidev.nav.currentPage -1) / ($slidev.nav.total -1)) * 100
  return Math.floor(p)
})
</script>

<template>
<Progress :percentage="num"/>
</template>

<style>
.top {
  color: rgb(55, 95, 255);
  font-size: 32px;
}
.progress {
  top: -20px;
  left: -45px;
}
</style>