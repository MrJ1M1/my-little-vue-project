<template>
    <from class="w-75 mx-auto" @submit.prevent>
        <h3>Note:</h3>
        <input type="text" v-model="information.text" placeholder="Enter text..." class="form-control mb-2">
        <h3>Day & Times:</h3>
        <input type="text" v-model="information.day" placeholder="Enter day & times..." class="form-control mb-2">
        <div class="check">
            <h3>MARK--></h3>
            <input type="checkbox" class="check_item" v-model="information.reminder">
        </div>
        <div class="text-center mb-5">
            <my-button @click="addTask" text="Save Task" class="w-75"></my-button>
        </div>
    </from>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            information:{
                text: '',
                day: '',
                reminder: false
            }
        }
    },  
    methods: {
        addTask(e){
            this.information.id = Date.now();
            this.$emit('addItem', this.information);
            this.information = {
                text: '',
                day: '',
                reminder: false
            }
        }
    },
}
</script>

<style scoped>
    .check{
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        margin-bottom: 10px;
    }
    .check_item{
        width: 30px;
        height: 50px;
    }
</style>