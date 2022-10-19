<template>
  <div class="main_box">
    <Header @toggle-add-task="toggleAddTask" :showVisible="showVisible" title="Track"/>
    <div v-if="showVisible">
      <AddTask @addItem="createTask"/>
    </div>
    <TaskList @toggle-item="toggleItem" @remove-item="removeItem" :informations="informations"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import TaskList from './components/TaskList.vue';
import AddTask from './components/AddTask.vue';
export default {
    components: { Header, TaskList, AddTask },
    data() {
      return {
        informations: [
          {id: 1, text: 'Barcelona was created', day: '1st February in 1890', reminder: true},
          {id: 2, text: 'Chelsea was created', day: '2nd April in 1889', reminder: false},
          {id: 3, text: 'Liverpool was created', day: '3rd July in 1895', reminder: true}
        ],
        showVisible: false,
      }
    },
    methods:{
      removeItem(id){
        if(confirm('Do you want to delete this task?')){
          this.informations = this.informations.filter((element) => element.id != id);
        }
      },
      toggleItem(id){
        this.informations = this.informations.map((element)=> element.id === id ? {...element, reminder: !element.reminder} : element);
      },
      createTask(information){
        if(information.text){
          this.informations.push(information);
        }
        else{
          alert('Complete the blanks!');
        }
      },
      toggleAddTask(){
        this.showVisible = !this.showVisible;
      }
    },
}
</script>

<style>
  .main_box{
    width: 500px;
    min-height: 300px;
    margin: 50px auto;
    border: 2px solid steelblue;
    border-radius: 15px;
    padding: 20px 30px;
  }
</style>