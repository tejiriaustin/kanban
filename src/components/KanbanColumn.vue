<template>
  <div class="column">
    <h2>{{ column.title }}</h2>
    <Task
        v-for="task in column.tasks"
        :key="task.id"
        :task="task"
    />
    <button @click="addTask">Add Task</button>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
import Task from '@/components/Task.vue'


const props = defineProps(['column'])

const addTask = () => {
  props.column.tasks.push({
    id: Date.now().toString(), // simple way to generate unique id
    title: 'New Task'
  })
}
</script>
