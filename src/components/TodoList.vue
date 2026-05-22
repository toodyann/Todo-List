<script setup>
import TodoItem from './TodoItem.vue';
import { ref } from 'vue';
import { defineEmits } from 'vue';

const {items} = defineProps(['items']);

const emit = defineEmits(['removeItem']);
</script>

<template>
    <div class="todo-list">
        <h2>To do List</h2>

        <TodoItem v-for="item in items" :item="item" :key="item.id" v-bind="item" @removeItem="emit('removeItem', item.id)"/>
    </div>
</template>

<style scoped>
.todo-list {
    text-align: center;
    padding: 20px;
}
</style>