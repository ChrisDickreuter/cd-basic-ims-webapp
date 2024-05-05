<script setup lang="ts">
import { onMounted, ref } from 'vue'

const items = ref<string[]>([])

onMounted(() => {
  items.value = ['item1', 'item2', 'item3']
})
</script>

<template>
  <main></main>
</template>
