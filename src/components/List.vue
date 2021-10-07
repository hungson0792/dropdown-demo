<template>
    <div>
        <input type="text" name="" id=" " v-model="newTodo">
        <button @click="addTodo()">Add</button>
        <div class="List">
             <Todo 
             v-for="(todo,index) in todos" 
             :key="index" 
             :todo="todo"
             :deleteTodo="deleteTodo"
             :index = "index"
             />
        </div>
       
    </div>
</template>

<script>
import Todo from './Todo.vue'

export default {
    data(){
        return {
            newTodo: '',
            todos: [
               
            ]
        }
    },
    methods:{
        addTodo(){
            this.todos.push({name:this.newTodo,done:false});
            this.newTodo = '';
        },
        deleteTodo(index){
            this.todos.splice(index,1)
        }
    },
    components: {
        Todo
    }
}
</script>

<style scoped>
    .List{
       font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;        
        color: #2c3e50;        
    }
</style>