<script>
export default {
    name: 'Home',
    data() {
        return {
            todo: "",
            todos: []
        }
    },
    methods: {
        addTodo() {
            if (this.todo && this.todo.trim()) this.todos = [...this.todos, this.todo];
            this.todo = "";
        },
        removeItem(i){
            this.todos=this.todos.filter((item,idx)=>idx!==i);
        }
    }
}
</script>

<template class="template-body">
<div class="input-box">
    <input type="text" placeholder="Enter a" name="todo" id="todo" v-model="todo">
    <button v-on:click="addTodo"> Add </button>
</div>
<ul v-for="(item,i) in todos" :key="i" class="ul-items">
    <li>{{ item }} <button v-on:click="removeItem(i)"> X </button></li>

</ul>
</template>

<style>
*{
    padding:0px;
    margin: 0px;
}
.template-body{
    height: 100vh;
    width: 100vw;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.input-box{
    height: 20%;
    width: 80%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    margin: 10px;
}
.ul-items{
    height: 70%;
    width: 80%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
</style>
