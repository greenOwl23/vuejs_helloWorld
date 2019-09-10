<template>
    <div>
        <div :key="item.id" v-for="item in todos">
            <TodoItem :input="item" v-on:del-todo="$emit('del-todo',item.id)"/>
        </div>
    </div>    
</template>
<script>
import TodoItem from './TodoItem.vue'
export default {
    name:"Todos",
    components:{
        TodoItem
    },
    props:["todos"]
}
</script>
<style scoped>

</style>