<script >
import TodoBoard from './components/TodoBoard.vue'

export default{
  data(){
    return{
      todos:[]
    }
  },
  
  methods:{
    removeTodos(index){
      console.log(index,"index")
            this.todos.splice(index, 1)
        },
    addTodo(todo,date){
      
        const newTodo = {
            id:this.todos.length+1,
            todo: todo,
            date: date
        }
        this.todos.push(newTodo)
        console.log(this.todos)
    }
  },
  components:{
    TodoBoard
  }
}

</script>

<template>
  <TodoBoard :todos="todos" @removeTodos="removeTodos" @addTodo="addTodo" />
</template>

<style>

</style>
