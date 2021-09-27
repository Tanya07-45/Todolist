<template>
  <div id="app">
   
    <div class="todo-wrapper">
      <div class="todo-container">
       <!-- <Todolist />sending arrays of todos -->
         <Todolist :todos="todos" />
         <div class="todo-create-btn-container">
          <div class="app-button">
            Create
          </div>
        </div>
      </div>
    </div>
      <div class="modal">
        <div class="modal-content">
          Modal Window
        </div>
    </div>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import playground from './playground.js'
import Todolist from '@/components/Todolist'

export default {
  name: 'App',
components:{
  Todolist
},
//function that returns object.
data() {
    return {
      todos: [
        {
          _id: '1',
          title: 'Walk the dog',
          description: 'Go to forrest near the Zoo'
        },
        {
          _id: '2',
          title: 'Buy a bread',
          description: 'Whole grain bread would be good'
        },
        {
          _id: '3',
          title: 'Learn Programming',
          description: 'Preferable Tomorrow!'
        }
      ]
    }
  },
  // This function is run automaticaly by VUE framework
  created() {
    playground()
  },
  
}
</script>

<style lang ="scss">
$colorrr:red;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.app-button {
  font-size: 20px;
  padding: 10px;
  border-radius: 5px;
  background-color: #795899;
  color: white;
  font-weight: bold;
  &:hover {
    cursor: pointer;
  }
}
.modal {
  display: none;
  position: fixed; // stay in place
  z-index: 9999;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto; // enable scroll if needed
  background-color: rgba(0, 0, 0, 0.4);
}
.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}


.todo {
  &-wrapper {
    /* flexible styling */
    display: flex;
     justify-content: center;
  /*flex-direction: column;*/
  width: 100%;
  /*height: 2000px;*/
    }
     &-create-btn-container {
    margin: 10px;
  }
&-container {
  display: flex;
  flex-direction: column;
  width: 400px;
  min-height: 400px;
  background-color:$colorrr;
  border-radius: 30px;
}

}


</style>
