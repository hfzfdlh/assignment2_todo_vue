<script>
export default{
    props:["todo"],
    created(){
        console.log(this.todo)
    }
}
</script>
<template>
    <div class="row">
        <div class="col form-check">
            <input class="form-check-input me-3" value="" type="checkbox">
            <label class="form-check-label">{{ todo.task }}</label>
        </div>
        <div class="col">
            <p>{{ todo.date }}</p>
        </div>
        <div class="col">
            <button @click="$emit('remove')" class="btn"><i class="bi bi-trash"></i></button>
        </div>
        
    </div>

</template>

<style>
</style>