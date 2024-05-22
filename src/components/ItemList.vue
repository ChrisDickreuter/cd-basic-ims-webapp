<script setup lang="ts">
import ItemDetail from "./ItemDetail.vue";

defineProps({
  items: { type: Array, required: true }
})
</script>

<template>
  <ul>
    <li v-for="item in items" :key="item.id">
      <ItemDetail :title="item.title" :description="item.description" />
    </li>
  </ul>
</template>
