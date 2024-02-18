<script>
export default{
    props:["todo","index"],
    emits:["removeTodos"],
    // created(){
    //     console.log(this.todo,this.index)
    // }
}
</script>
<template>
    <div class="row">
        <div class="col form-check">
            <input class="form-check-input me-3" value="" type="checkbox">
            <label class="form-check-label">{{ todo.todo }}</label>
        </div>
        <div class="col">
            <p>{{ todo.date }}</p>
        </div>
        <div class="col">
            <button @click="$emit('removeTodos',this.index)" class="btn"><i class="bi bi-trash"></i></button>
        </div>
        
    </div>

</template>

<style>

</style>