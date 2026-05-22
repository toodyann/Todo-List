<script setup>
import { defineEmits } from 'vue';

const emit = defineEmits(['removeItem']);

const {id, text} = defineProps(['id', 'text']);
</script>

<template>
    <div class="todo-item" :data-id="id">
        <p class="todo-item-text">{{ text }}</p>
        <button @click="emit('removeItem', id)">Remove</button>
    </div>
</template>

<style scoped>
.todo-item {
    text-align: center;
    padding: 20px;
}
</style>