<template>
  <div id="app">
    <todo-header></todo-header>
    <todo-input></todo-input>
    <todo-list></todo-list>
    <todo-footer></todo-footer>
  </div>
</template>

<script>
  import TodoHeader from "./components/TodoHeader";
  import TodoInput from "./components/TodoInput";
  import TodoList from "./components/TodoList";
  import TodoFooter from "./components/TodoFooter";

  export default {
    // data(){
    //   return{
    //     todoItems: []
    //   }
    // },
    // methods:{
    //   addOneItem(todoItem){
    //     const obj = {completed:false, item:todoItem};
    //     localStorage.setItem(todoItem, JSON.stringify(obj));
    //     this.todoItems.push(obj);
    //   },
    //   removeOneItem(todoItem, index){
    //     localStorage.removeItem(todoItem.item);
    //     this.todoItems.splice(index, 1);
    //   },
    //   toggleOneItem(todoItem, index) {
    //     console.log(todoItem);
    //     this.todoItems[index].completed = !this.todoItems[index].completed;
    //     localStorage.removeItem(todoItem.item);
    //     localStorage.setItem(todoItem.item, JSON.stringify(todoItem));
    //   },
    //   clearAllItems(){
    //     localStorage.clear();
    //     this.todoItems = [];
    //   },
    // },
    components: {TodoFooter, TodoList, TodoInput, TodoHeader},
  }
</script>

<style>
  body {
    text-align: center;
    background-color: #F6F6F8;
  }

  input {
    border-style: groove;
    width: 200px;
  }

  button {
    border-style: groove;
  }

  .shadow {
    box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
  }
</style>
