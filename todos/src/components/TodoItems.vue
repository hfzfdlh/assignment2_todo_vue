<script>
export default{
    props:["todo","index"],
    emits:["deleteTodo","changeStatusTodo"],
    // created(){
    //     console.log(this.todo,this.index)
    // }
}
</script>
<template>
    <div class="row ">
        <div class="col form-check">
            <input class="form-check-input me-3" value="" type="checkbox" @change="$emit('changeStatusTodo',this.index)">
            <!-- <label class="form-check-label">{{ todo.todo }}</label> -->
            <label v-if="this.todo.status === false" class="form-check-label">{{ todo.todo }}</label>
            <label v-else class="form-check-label text-decoration-line-through">{{ todo.todo }}</label>
        </div>
        <div class="col">
            <button class="btn btn-outline-warning" disabled>{{ todo.createdDate }}</button>
        </div>
        <div class="col">
            <div class="row">
                <button @click="$emit('deleteTodo',this.index)" class="btn"><i class="bi bi-trash"></i></button>
            </div>
            <div class="row">
                <p>{{ todo.date }}</p>
            </div>
        </div>
    </div>

</template>

<style>

</style>