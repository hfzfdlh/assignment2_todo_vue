<script>
import TodoItems from './TodoItems.vue'
export default{
    props:["todos"],
    components:{
        TodoItems
    },
    emits:["deleteTodo","addTodo","changeStatusTodo"],
    data(){
        return{
            todo:'',
            date:''
        }
    }, methods:{
        deleteTodo(index){
            this.$emit('deleteTodo',index)
        },
        changeStatusTodo(index){
            this.$emit('changeStatusTodo',index)
        }
    }
}
</script>

<template>
    <div class="container w-100 border rounded px-5">
        <h1 class="text-center pb-5">My Todo-s</h1>
        <div class="row">
            <div class="col">
                <input 
                    v-model="todo"
                    class="form-control"
                    placeholder="Add new..."
                />
            </div>
            <div class="col">
                <input
                    type="date"
                    v-model="date"
                    class="form-control"/>
            </div>
            <button class="btn btn-primary mb-2" @click="$emit('addTodo',this.todo,this.date)">Add</button>

            <TodoItems class="py-2" v-for="(todo, index) in todos" :key="todo.id" @deleteTodo="deleteTodo" @changeStatusTodo="changeStatusTodo" :todo="todo" :index="index"></TodoItems>
        </div>

     

    </div>
    <div>
        
    </div>

</template>

<style scoped>
div{
    margin:20px 10%;
}
</style>