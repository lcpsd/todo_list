<template>
  <div class="task-grid">
      <template v-if="tasks.length">
          <task v-for="task in tasks" :key="task.name" :task="task"></task>
      </template>
      <p v-else class="no-task">Sua vida está em dia!</p>
  </div>
</template>

<script>

import task from './task.vue'

export default {
    components: {task},
    props:{
        tasks: {type: Array, required: true}
    }
}
</script>

<style>
    .task-grid{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .task-grid .task{
        margin: 10px;
    }

    .no-task{
        color: white;
        font-size: 20px;
    }
</style>