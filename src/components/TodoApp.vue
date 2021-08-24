<template>
  <body>
    <h1 class="heading">TODO APP <i class="fab fa-vuejs fa-xs icon"></i></h1>
      <div class="inputDiv">
        <input class="input" type="text" v-model="todo" placeholder="Enter your todo here"/>
      </div>
      <div class="inputPriority">
        <input class="input" type="text" @keypress="validateNumber" v-model="priority" placeholder="Enter your priority here"/>
      </div>
      <!-- <div id="output-box"></div> -->
      <h4 v-if="isError">Text field required.</h4>
      <h4 v-if="isErrorNum">Please enter number only.</h4>
        <button class="addButton" @click="storeTodo">
          <i class="fas fa-plus fa-2x"></i>
        </button>
      <div class="container">
        <div class="item" v-for="(todo, index) in todos" :key="index">
          <div class="itemInput" :class="{'strikeout': todo.isStrikedOff == true}">
            {{todo.seq}}
            {{todo.name}}
          </div>
            <button class="doneTodo" @click="doneTodo(index)">Done</button>
            <button class="removeTodo" @click="removeTodo(index)">Remove</button>
        </div>
      </div>
      <!-- <div class="items">
        <div class="item" v-for="(todo, index) in removedTodos" :key="index">
          <div class="itemInput">
            {{todo.seq}}
            {{todo.name}}
          </div>
        </div>
      </div> -->
    <div id="footer">
      <p><a href="https://github.com/soham-dixit/todo-app-vuejs-cli" target="_blank">Source code</a></p>
    </div>
  </body>
</template>

<script>
export default {
  name: "TodoApp",

  data(){
    return {
      todo: "",
      priority: "",
      // priorities: [],
      todos: [],
      removedTodos: [],
      removedTodo: "",
      isError: false,
      isErrorNum: false
    }
},

  methods: 
  {
    validateNumber()
      {
        let keyCode = event.keyCode;
        if(keyCode < 48 || keyCode > 57)
        {
          event.preventDefault();
          this.isErrorNum = true
          // alert("Please enter num");
          // document.getElementById("output-box").innerHTML += "Sorry! <code>preventDefault()</code> won't let you check this!<br>";
        }

        else{
          this.isErrorNum = false
        }
      },

    storeTodo() 
    {
      if (this.todo != "" && this.priority != "")
      {
        this.todos.push({name: this.todo, seq:Number(this.priority), isStrikedOff: false});
        //sort this.todos array
        this.todos.sort( (a, b) => { return a.seq - b.seq} )
        this.priority = "";
        this.todo = "";
        this.isError=false
        // this.priorities.sort((a, b) => (a.priority > b.priority) ? -1 : 1);
      }

      else 
      {
        this.isError=true
      }
    },

    removeTodo(index) 
    {
      // this.todos[index].isStrikedOff=true;
      // this.removedItems();
      this.todos.splice(index, 1);
      this.priorities.splice(index, 1);
    },

    doneTodo(index)
    {
        this.todos[index].isStrikedOff=true;
    },

    // removedItems()
    // {
    //   this.removedTodos.push({name:this.todos.concat(this.removedTodo)})
    // }
  },
};
</script>