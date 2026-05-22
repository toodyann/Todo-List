<script setup>
import TodoList from '../components/TodoList.vue';
import AddTodo from '../components/AddTodo.vue';
import { ref } from 'vue';
    
const items = ref([
    { id: 1, text: 'Buy groceries' },
    { id: 2, text: 'Walk the dog' },
    { id: 3, text: 'Read a book' }
]);

const addItem = (text) => {
    const newItem = {
        id: Date.now(),
        text
    };
    items.value.push(newItem);
};

const removeItem = (id) => {
    items.value = items.value.filter(item => item.id !== id);
};
</script>

<template>
    <div class="home">
        <h1>ToDo List App</h1>
        <AddTodo @addItem="addItem" />
        <TodoList :items="items" @removeItem="removeItem" />

    </div>
</template>

<style scoped>
.home {
    text-align: center;
    padding: 20px;
}
</style>