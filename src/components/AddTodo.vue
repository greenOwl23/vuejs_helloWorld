<template>
    <div>
        <form @submit="addTodo">
            <input v-model="title" type="text" name="title" placeholder="Add todo..." id="">
            <input class="btn" type="submit" name="" value="Submit" id="">
        </form>
    </div>
</template>
<script>
export default {
    name:"AddTodo",
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo ={
                title:this.title,
                status:false
            }
            this.$emit('add-todo',newTodo);
            this.title='';
        }
    }
}
</script>
<style  scoped>
    form{
        display: flex;

    }
    input[type="text"]{
        flex:10;
        padding: 5px;
    }
</style>