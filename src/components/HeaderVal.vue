<template>
    <header>
        <h1>
            {{title}}
        </h1>
        <Button 
        v-show="homePage"
        @btn-click="$emit('show-add-toggle')"
        :text="showAddTask ? 'Close' : 'AddTask'" 
        :color="showAddTask ? 'red' : 'blue'"  />
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'HeaderVal',
    props: {
        title: String,
        showAddTask: Boolean
    },
    components: {
        Button
    },
    computed: {
        homePage() {
           if (this.$route.path === '/') {
               return true
           } else {
               return false
           }
        }
    }
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
