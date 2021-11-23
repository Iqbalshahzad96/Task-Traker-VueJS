<template>
    <header>
        <h1>{{ title }}</h1>
        <h3>{{ count }}</h3>
        <Button 
        @btn-click="addTask()"
        text='Add Task' color='green'/>
        <Button 
        @btn-click="deleteTask()"
        text='Delete Task' color='red'/>
    </header>
</template>

<script>
import Button from './Button'

export default{
    name: 'Header',
    props: {
        title: String,
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
        },
        deleteTask() {
            this.count -= 1
        },
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