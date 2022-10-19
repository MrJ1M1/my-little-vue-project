<template>
    <div @dblclick="$emit('toggle-item', information.id)" :class="[information.reminder ? 'reminder' : '' ,'task_item']">
        <h4>{{information.text}} <i @click="$emit('remove-item', information.id)" class="fas fa-times"></i></h4>
        <p>{{information.day}}</p>
    </div>
</template>

<script>
export default {
    name: 'TaskItem',    
    props: {
        information: {
            type: Object,
            required: true
        }
    },
    emits: ['toggle-item', 'remove-item'],

}
</script>

<style scoped>
    .task_item{
        background: #f4f4f4;
        margin: 5px;
        padding: 10px 20px;
    }
    .task_item h4{
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    .task_item.reminder{
        border-left: 5px solid green;
    }
    .fas{
        color: red;
    }
</style>