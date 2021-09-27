<template>
  <div id="app">
   
    <div class="todo-wrapper">
      <div class="todo-container">
       <Todolist />
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

  // This function is run automaticaly by VUE framework
  created() {
    playground()
  },
  
}
</script>

<style lang ="scss" scoped>
$colorrr:red;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
&-container {
  width: 400px;
  min-height: 400px;
  background-color:$colorrr;
  border-radius: 50px;
}

}


</style>
