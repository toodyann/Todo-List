<script setup>
import { ref, defineEmits } from 'vue';

const text = ref('');

const emit = defineEmits(['addItem']);

const onSubmit = (e) => {
    e.preventDefault();
    if (text.value.trim() === '') return;

    emit('addItem', text.value);
    text.value = '';
};

</script>

<template>
<div class="todo-form">

    <h2>Add ToDo Item</h2>

    <form @submit.prevent="onSubmit">
        <input v-model="text" type="text" placeholder="Enter new todo item" />
        <button type="submit">Add</button>
    </form>

</div>
</template>

<style scoped>
.todo-form {
    text-align: center;
    padding: 20px;
}
</style>