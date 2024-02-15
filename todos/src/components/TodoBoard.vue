<script>
import TodoItems from './TodoItems.vue'
export default{
    props:["todos"],
    components:{
        TodoItems
    },
    data(){
        return{
            task:'',
            date:''
        }
    },
    methods:{
        addTask(){
            const newTask = {
                id:this.todos.length+1,
                task: this.task,
                date: this.date
            }
            this.todos.push(newTask)
            console.log(this.todos)
        },

        removeTodos(index){
            this.todos.splice(index, 1)
        }
    }
}
</script>

<template>
    <div class="container border rounded px-5">
        <h1 class="text-center pb-5">My Todo-s</h1>
        <div class="row">
            <div class="col">
                <input 
                    v-model="task"
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
            <button class="btn btn-primary mb-2" @click="addTask">Add</button>

            <TodoItems class="py-2" v-for="todo in todos" :key="todo.id" @remove="removeTodos(index)" :todo="todo"></TodoItems>
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