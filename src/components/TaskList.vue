<template>
    <div v-for="information in informations" :key="information.id">
        <TaskItem @toggle-item="$emit('toggle-item', information.id)" @remove-item="$emit('remove-item', information.id)" :information="information"/>
    </div>
</template>

<script>
import TaskItem from './TaskItem.vue';
export default {
    name: "TaskList",
    props: {
        informations: {
            type: Array,
            required: true
        }
    },
    components: { TaskItem },
    emits: ['toggle-item', 'remove-item'],
}
</script>

<style scoped>
    
</style>