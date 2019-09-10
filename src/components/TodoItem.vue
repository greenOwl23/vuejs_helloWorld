<template>
    <div class="todo-item" :class="{'is-complete':input.completed}">
        <input type="checkbox" v-on:change="markComplete" >{{ input.title}}
        <button @click="$emit('del-todo',input.id)" class="del">x</button>
    </div>
</template>
<script>
export default {
    name:"TodoItem",
    props:["input"],
    methods:{
        markComplete(){
            this.input.completed = !this.input.completed;
            
        }
    }
}
</script>
<style scoped>
    .todo-item{
        background: white;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }
    .is-complete{
        text-decoration: line-through;
    }
    .del{
        background: red;
        color: white;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        float: right;
        cursor: pointer;
    }
</style>