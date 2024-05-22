<script setup lang="ts">
import { ref } from 'vue';

const emit = defineEmits(['add-item'])

const title = ref('')
const description = ref('')

const onSubmit = () => {
    const item = { title: title.value, description: description.value }
    emit('add-item', item)
    title.value = ''
    description.value = ''
}
</script>

<template>
    <form @submit.prevent="onSubmit">
        <label for="title">Title</label>
        <input type="text" v-model="title" name="title" required>
        <label for="description">Description</label>
        <textarea v-model="description" name="description" required></textarea>
        <button type="submit">Add</button>
    </form>
</template>