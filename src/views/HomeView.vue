<script setup lang="ts">
import { onMounted, ref } from 'vue'
import ItemList from '@/components/ItemList.vue'
import ItemForm from "@/components/ItemForm.vue";

const items = ref<Object[]>([])

onMounted(() => {
  items.value = [
    { id: 1, title: 'item1', description: 'description1' },
    { id: 2, title: 'item2', description: 'description2' },
    { id: 3, title: 'item3', description: 'description3' }
  ]
})

const addItem = (item: { title: string, description: string }) => {
  items.value.push({
    id: items.value.length + 1,
    title: item.title,
    description: item.description
  })
}
</script>

<template>
  <main>
    <h1>Home</h1>
    <ItemList :items="items" />
    <ItemForm @add-item="addItem" />
  </main>
</template>
