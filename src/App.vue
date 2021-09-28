<template>
  <div id="app">
   
    <div class="todo-wrapper">
      <div class="todo-container">
       <!-- <Todolist />sending arrays of todos -->
       <!-- //custom components -->
         <Todolist :tothe="todos" /> 
         <div class="todo-create-btn-container">
          <!-- <div v-on:click="openModal" class="app-button"> -->
             <div @click="openModal" class="app-button">
            Create
          </div>
        </div>
      </div>
    </div>
    <modal 
    v-on:modalClosed="closeModal"
    :isOpen="isModalOpen" />

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import playground from './playground.js'
import Todolist from '@/components/Todolist'
import modal from '@/components/modal'


export default {
  name: 'App',
components:{
  Todolist,modal
},
//function that returns object.
data() {
    return {
      isModalOpen: false,
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
  methods:{
    openModal(){
      //  this.isModalOpen = !this.isModalOpen
       this.isModalOpen = true
      // alert("opening modal!!!!")
    },
    closeModal(data){
      alert(data.value)
     this.isModalOpen = false
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
