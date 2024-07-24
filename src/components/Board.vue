<template>
  <div class="board">
    <Column
        v-for="column in columns"
        :key="column.id"
        :column="column"
    />
  </div>
</template>

<script>
import Column from '@/components/KanbanColumn.vue'

export default {
  name: 'Kanban-Board',
  components: {
    Column
  },
  data() {
    return {
      columns: [
        { id: 1, title: 'To Do', tasks: [] },
        { id: 2, title: 'In Progress', tasks: [] },
        { id: 3, title: 'Done', tasks: [] }
      ]
    }
  }
}
</script>