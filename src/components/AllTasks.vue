<template>
    <div @dblclick ="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder': '','task']">
        <h3>{{ task.text }}
            <i @click="$emit('delete-task',task.id)" class="fa-solid fa-trash"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>
export default {
    name: 'AllTasks',
    props: {
        task: Object,
    },
    
}
</script>

<style scope>
.fa-solid{
    color: red;
    float: right;
    margin-top: 11px;
}
.task{
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}
.task.reminder{
    border-left: 5px solid green;
}
.task h3{
    display: fle;
    align-items: center;
    justify-content: space-between;
}
</style>