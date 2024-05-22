<script setup lang="ts">
import { useForm } from "vee-validate"
import * as yup from "yup";

const emit = defineEmits(['add-item'])

const { errors, handleSubmit, defineField } = useForm({
    validationSchema: yup.object({
        title: yup.string().required(),
        description: yup.string().required()
    })
})

const onSubmit =  handleSubmit(values => {
        emit('add-item', values)
        title.value = ''
        description.value = ''
    })


const [title, titleAttrs] = defineField('title')
const [description, descriptionAttrs] = defineField('description')
</script>

<template>
    <form @submit.prevent="onSubmit">
        <label for="title">Title</label>
        <input type="text" v-model="title" v-bind="titleAttrs" id="title">
        <div>{{ errors.title }}</div>
        <label for="description">Description</label>
        <textarea v-model="description" v-bind="descriptionAttrs" id="description"></textarea>
        <div>{{ errors.description }}</div>
        <button type="submit">Add</button>
    </form>
</template>