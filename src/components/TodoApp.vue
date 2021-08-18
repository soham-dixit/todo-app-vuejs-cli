<template>
  <body>
    <h1 class="heading">TODO APP <i class="fab fa-vuejs fa-xs icon"></i></h1>
      <div class="inputDiv">
        <input class="input" type="text" v-model="todo" placeholder="Enter your todo here"/>
        <button class="addButton" @click="storeTodo">
          <i class="fas fa-plus fa-2x"></i>
        </button>
      </div>
      <div class="container">
        <div class="item" v-for="(todo, index) in todos" :key="index">
          <div class="itemInput" :class="{'strikeout': todo.isStrikedOff == true}">
            {{ todo.name }}
          </div>
            <button class="doneTodo" @click="doneTodo(index)">Done</button>
            <button class="removeTodo" @click="removeTodo(index)">Remove</button>
        </div>
      </div>
    <div id="footer">
      <p><a href="https://github.com/soham-dixit/todo-app-vuejs" target="_blank">Source code</a></p>
    </div>
  </body>
</template>

<script>
export default {
  name: "TodoApp",

  data(){
    return {
      todo: "",
      todos: [],
      selectedTodo: null,
    }
},

  methods: 
  {
    storeTodo() 
    {
      if (this.todo != "") 
      {
        this.todos.push({name: this.todo, isStrikedOff: false});
        this.todo = "";
      }
    },

    removeTodo(index) 
    {
      this.todos.splice(index, 1);
    },

    doneTodo(index)
    {
        this.todos[index].isStrikedOff=true;
    },
  },
};
</script>