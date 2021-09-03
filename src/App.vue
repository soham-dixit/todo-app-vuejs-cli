<template>
  <div id="app">
    <todoApp></todoApp>
  </div>
</template>

<script>
import TodoApp from './components/TodoApp.vue'

export default {
  name: 'App',
  components: {
    TodoApp
  }
}
</script>

<style>
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

.sub-container {
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
  margin: 1rem 0 1rem;
  text-align: center;
}

h4{
  font-family: 'Courier New', Courier, monospace;
  color: red;
  display: flex;
  justify-content: center;
  align-items: center;
}

.heading {
  font-family: "Sriracha", cursive;
  font-weight: 800;
  color: yellow;
}

.sub-heading{
  font-family: "Sriracha", cursive;
  font-weight: 800;
  color: yellow;
  font-size: 1.8rem;
  margin-top: -1rem;
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
  height: 40px;
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

.inputPriority {
  display: flex;
  justify-content: center;
  align-items: center;
}

.inputPriority .input {
  padding: 0.5rem 1rem;
  height: 40px;
  outline: none;
  border: none;
  width: 350px;
  font-size: 1.15rem;
  margin: 0.25rem;
  transition: 0.5s;
  border-radius: 25px;
}

.inputPri:hover {
  box-shadow: 0 0 10px 3px yellow;
}

.itemPriority{
  font-family: "Sriracha", cursive;
  font-size: 15px;
  color: yellow;
}

.addButton {
  height: 40px;
  width: 40px;
  border-radius: 25px;
  outline: none;
  border: none;
  background-color: #a0a4d9;
  color: black;
  margin-top: 0.5rem;
  margin-left: 48.5%;
  cursor: pointer;
  transition: 0.5s;
}

.addButton:hover {
  transform: rotate(90deg);
  color: rgb(0, 255, 21);
  box-shadow: 0 0 10px 3px #a0a4d9;
}

.removeTodo {
  font-size: 15px;
  font-family: "Sriracha", cursive;
  background: none;
  outline: none;
  color: red;
  border: none;
  cursor: pointer;
  margin-left: 2rem;
}

.deleteTodo {
  font-size: 15px;
  font-family: "Sriracha", cursive;
  background: none;
  outline: none;
  color: red;
  border: none;
  cursor: pointer;
  margin-left: 2rem;
}

.retrieveTodo {
  font-size: 15px;
  font-family: "Sriracha", cursive;
  background: none;
  outline: none;
  color: rgb(0, 217, 255);
  border: none;
  cursor: pointer;
}

.doneTodo {
  font-size: 15px;
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

.removedItem {
  padding: 0.5rem;
  margin-bottom: 1.5rem;
  border: 2px solid #fff;
  transition: 0.5s;
}

.removedItem:hover {
  box-shadow: 0 0 10px 3px red;
}

.itemInput {
  background: none;
  font-family: "Sriracha", cursive;
  outline: none;
  color: #fff;
  border: none;
  width: 245px;
  font-size: 15px;
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

/* .removedTodos{
  background-color: rgba(255, 255, 255, 0.185);
  opacity: 0.5;
} */

.removedItems{
  background: none;
  font-family: "Sriracha", cursive;
  outline: none;
  color: #fff;
  border: none;
  width: 245px;
  font-size: 15px;
}

.desc{
  font-size: 15px;
  color: rgb(158, 158, 158);
  white-space: pre-wrap; 
  word-wrap: break-word;
}
</style>