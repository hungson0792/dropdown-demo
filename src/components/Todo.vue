<template>
    <div>
        <span class="checkbox" 
        :class="{checked:todo.done}"
        @click="todo.done = !todo.done"
        ></span>
        <!-- <input type="checkbox" name="" id="" v-model="todo.done"> -->
        <span :class="{done:todo.done}">
            {{todo.name}}
            <a href="#" @click.prevent="deleteTodo(index)">Xóa</a>
            </span>
    </div>
    
</template>

<script>


export default {
    props: ['todo','deleteTodo','index'],
    data(){
        return {
            
        }
    }
}
</script>

<style scoped>
    span.done{
        text-decoration: line-through;
    }
    .checkbox{
       display: inline-block;
       width: 20px;
       height: 20px;
       border: 1px solid black;
    }
    .checkbox.checked{
        background-color: red;
    }
</style>