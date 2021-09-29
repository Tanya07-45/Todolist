<template>
  <div id="app">
   
    <div class="todo-wrapper">
      <div class="todo-container">
       <!-- <Todolist />sending arrays of todos -->
       <!-- //custom components -->
         <Todolist :tothe="todos" /> 
         <div class="todo-create-btn-container">
        
              <todocreate  @formSubmitted="createTodo" />
        </div>
      </div>
    </div>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import playground from './playground.js'
import Todolist from '@/components/Todolist'
import todocreate from '@/components/Todocreate'
import store from '@/store'

export default {
  name: 'App',
components:{
  Todolist,todocreate
},
//function that returns object.
data() {
    return {
      todos: store.state.todos
    }
  },
  // This function is run automaticaly by VUE framework
  created() {
    playground()
     },
  methods: {
    createTodo(todo) {
     store.createTodo(todo)
    }
  }

  
}
</script>

<style lang ="scss">
$colorrr:red;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.app-error {
  color: #ff1212;
}
.app-form {
    .label {
      display: block;
      font-size: 18px;
      font-weight: bold
    }
    .form-input {
      padding: 10px;
      font-size: 17px;
    }
    .form-input {
      padding: 10px;
      font-size: 17px;
    }
    .form-control {
      margin-bottom: 10px;
      &-last {
      margin-bottom: 0;
    }
    }
  }
.is-primary {
  background-color: #53b0ee !important;
}
.is-warning {
  background-color: #6453ff !important;
}
.is-danger {
  background-color: #f80404 !important;
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
  background-color:black;
  border-radius: 30px;
}

}


</style>
