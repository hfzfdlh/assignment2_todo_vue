<script >
import TodoBoard from './components/TodoBoard.vue'

export default{
  data(){
    return{
      todos:[]
    }
  },
  components:{
    TodoBoard
  }
}

</script>

<template>
  <TodoBoard :todos="todos"/>
</template>

<style>

</style>
