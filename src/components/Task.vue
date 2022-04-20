<template>
    <div
    @dblclick="$emit('reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
        {{task.text}}
        <i
        @click="onDelete(task.id)" 
        class="fas fa-times"></i>
    </h3>
    <p>
        {{task.id}}
    </p>
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-task', id)
        }
    },
    emits: ['delete-task', 'reminder'],
}
</script>
<style scoped>

.task {
  margin: 5px;
  background: #f4f4f4;
  padding: 10px 20px;
  cursor: pointer;
}
.task h3 {
    display: flex;
    align-items: center;
   justify-content: space-between;
}
.fas {
    color: blue;
}
.task.reminder {
    border-left: 5px solid blue;
}

</style>
