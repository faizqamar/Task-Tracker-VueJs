<template>
    <div :key="task.id" v-for="task in tasks">
    <AllTasks @toggle-reminder="$emit('toggle-reminder', task.id)"
     @delete-task="$emit('delete-task', task.id)" :task = "task"/>
</div>
</template>

<script>
import AllTasks from './AllTasks.vue'

    export default {
        name: 'TasksList',
        props: {
            tasks: Array,
        },
        components: {
            AllTasks
        },
        emits: ['delete-task', 'toggle-reminder'],
    }
</script>