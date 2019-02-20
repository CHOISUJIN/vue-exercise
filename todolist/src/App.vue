<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
    <TodoList v-bind:propsdata="todoItems" v-on:removeTodo="removeTodo"></TodoList>
    <TodoFooter v-on:RemoveAll="RemoveAll"></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader';
import TodoInput from './components/TodoInput';
import TodoList from './components/TodoList';
import TodoFooter from './components/TodoFooter';

export default {
  name: 'app',
  data () {
    return {
      todoItems : []
    }
  },
  created() {
    if(localStorage.length > 0)
    {
      for(var i=0; i < localStorage.length; i++ )
      {
        this.todoItems.push(localStorage.key(i));
      }
    }
  },
  methods: {
    addTodo(value) {
      this.todoItems.push(value);
    },
    removeTodo(index) {
      localStorage.removeItem(index);
      this.todoItems.splice(index,1);
    },
    RemoveAll(){
      localStorage.clear();
      this.todoItems =[];
    }
  },
  components : {
    'TodoHeader': TodoHeader,
    'TodoInput': TodoInput,
    'TodoList': TodoList,
    'TodoFooter':TodoFooter
  }
}
</script>

<style>
body{
  text-align: center;;
  background-color: #f6f6f8;
}

input{
  border-style: groove;
  width: 200px;
}

button{
  border-style: groove;
}

</style>
