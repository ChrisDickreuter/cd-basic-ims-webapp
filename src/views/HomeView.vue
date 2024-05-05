<script setup lang="ts">
import { onMounted, ref } from 'vue'

const items = ref<Object[]>([])

onMounted(() => {
  items.value = [
    { id: 1, title: 'item1', description: 'description1' },
    { id: 2, title: 'item2', description: 'description2' },
    { id: 3, title: 'item3', description: 'description3' }
  ]
})
</script>

<template>
  <main></main>
</template>
