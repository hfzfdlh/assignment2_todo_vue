<script >
import TodoBoard from './components/TodoBoard.vue'

export default{
  data(){
    return{
      todos:[]
    }
  },
  
  methods:{
    deleteTodo(index){
      console.log(index,"index")
            this.todos.splice(index, 1)
        },
    addTodo(todo,date){
        let currDate = new Date()
        const options = {
          weekday: 'short',
          year: 'numeric',
          month: 'numeric',
          day: 'numeric',
        };

        let taskDate = new Date(date)
      
        const newTodo = {
            id:this.todos.length+1,
            todo: todo,
            date: taskDate.toLocaleDateString("en-CA", options),
            createdDate: currDate.toLocaleDateString("en-CA", options),
            status:false
        }
        this.todos.push(newTodo)
        console.log(this.todos)
    },
    changeStatusTodo(index){

      if (this.todos[index]['status']) this.todos[index]['status'] = false
      else{
        this.todos[index]['status'] = true
      }
    }
  },
  components:{
    TodoBoard
  }
}

</script>

<template>
  <TodoBoard :todos="todos" @deleteTodo="deleteTodo" @addTodo="addTodo" @changeStatusTodo="changeStatusTodo" />
</template>

<style>

</style>
