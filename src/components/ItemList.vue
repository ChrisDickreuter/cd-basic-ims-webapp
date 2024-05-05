<script setup lang="ts">
defineProps({
  items: Array
})
</script>

<template>
  <ul>
    <li v-for="item in items" :key="item.id">
      <h2>{{ item.title }}</h2>
      <p>{{ item.description }}</p>
    </li>
  </ul>
</template>
