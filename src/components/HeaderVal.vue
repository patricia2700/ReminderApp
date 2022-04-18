<template>
    <header>
        <h1>
            {{title}}
        </h1>
        <Button text="Add Task" color="blue" />
        <Button text="Update Task" color="green" />
        <Button text="Update Task" color="red" />
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'HeaderVal',
    props: {
        title: String,
    },
    components: {
        Button
    },
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 10px;
    }
</style>
