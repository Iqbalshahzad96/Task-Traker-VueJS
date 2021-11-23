<template>
    <header>
        <h1>{{ title }}</h1>
        <h3>{{ count }}</h3>
        <Button 
        @btn-click="$emit('toggle-add-task')"
        :text="showAddTask ? 'Close' : 'Add Task'"
        :color="showAddTask ? 'red' : 'green'" />
    </header>
</template>

<script>
import Button from './Button'

export default{
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean,
    },
    data() {
        return {
            count : 0
        }
    },
    components: {
        Button,
    },
    methods: {
        addTask() {
            this.count += 1
        }
    },
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>