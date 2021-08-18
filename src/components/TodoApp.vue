<template>
  <div id="body">
    <h1 class="heading">TODO APP <i class="fab fa-vuejs fa-xs icon"></i></h1>
      <div class="inputDiv">
        <input
          class="input"
          type="text"
          v-model="todo"
          placeholder="Enter your todo here"
        />
        <button class="addButton" @click="storeTodo">
          <i class="fas fa-plus fa-2x"></i>
        </button>
      </div>
      <div class="container">
        <!-- <div class="item" v-for="(todo, index) in todos"> -->
          <div
            class="itemInput"
            :class="{'strikeout': todo.isStrikedOff == true}"
          >
            {{ todo.name }}
          </div>
          <button class="doneTodo" @click="doneTodo(index)">Done</button>
          <button class="removeTodo" @click="removeTodo(index)">Remove</button>
        </div>
      </div>
    <!-- </div> -->
    <div id="footer">
      <p>
        <a href="https://github.com/soham-dixit/todo-app-vuejs" target="_blank"
          >Source code</a
        >
      </p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

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

<style scoped>
  * {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  height: 100%;
  background-color: #27282c;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin-top: 2rem;
}

h1 {
  font-size: 3rem;
  font-weight: 50;
  margin: 1rem 0 3rem;
  text-align: center;
}

.heading {
  font-family: "Sriracha", cursive;
  font-weight: 800;
  color: yellow;
}

.icon {
  color: #41b883;
}

.inputDiv {
  display: flex;
  justify-content: center;
  align-items: center;
}

.inputDiv .input {
  padding: 0.5rem 1rem;
  height: 50px;
  outline: none;
  border: none;
  width: 350px;
  font-size: 1.15rem;
  margin: 0.25rem;
  transition: 0.5s;
  border-radius: 25px;
}

.input:hover {
  box-shadow: 0 0 10px 3px yellow;
}

.addButton {
  height: 50px;
  width: 50px;
  border-radius: 25px;
  outline: none;
  border: none;
  background-color: #a0a4d9;
  color: black;
  margin: 0.25rem;
  cursor: pointer;
  transition: 0.5s;
}

.addButton:hover {
  transform: rotate(90deg);
  color: rgb(0, 255, 21);
  box-shadow: 0 0 10px 3px #a0a4d9;
}

.removeTodo {
  font-size: 1rem;
  font-family: "Sriracha", cursive;
  background: none;
  outline: none;
  color: red;
  border: none;
  cursor: pointer;
}

.doneTodo {
  font-size: 1rem;
  margin: 0 0.5rem;
  font-family: "Sriracha", cursive;
  background: none;
  outline: none;
  color: rgb(0, 255, 38);
  border: none;
  cursor: pointer;
}

.item {
  padding: 0.5rem;
  margin-bottom: 1.5rem;
  border: 2px solid #fff;
  transition: 0.5s;
}

.item:hover {
  box-shadow: 0 0 10px 3px yellow;
}

.itemInput {
  background: none;
  outline: none;
  color: #fff;
  border: none;
  width: 245px;
  font-size: 1rem;
}

#footer * {
  background-color: #212121;
  height: 60px;
  position: fixed;
  bottom: 0px;
  left: 0px;
  line-height: 50px;
  color: #aaa;
  text-align: center;
  width: 100%;
  text-decoration: none;
  font-family: "Ubuntu", sans-serif;
}

.strikeout{
  text-decoration: line-through;
}
</style>
