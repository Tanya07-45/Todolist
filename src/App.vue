<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1>Hello world </h1>
    <div> {{text}}</div>
     <div>{{someNumber}}</div>
    <div>{{canDecide}}</div>
    <div>{{someObject}}</div>
    <div>{{someObject.a}}</div>
    <div>{{someObject.c}}</div>
    <div>{{dataFunction}}</div>
    <div>{{dataFunction()}}</div>
    <!-- <div>{{testFunctionA()}}</div> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import playground from './playground.js'
export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // },
  data() {
    return {
      text: 'Some String value',
      someNumber: 16,
      canDecide: true,
      list: [1,2,3],
      someObject: {
        a: 1,
        b: 2,
        c: [1,2,3,4,5]
      },
      dataFunction() {
        console.log('Data function')
        return 'I am Data function'
      }
    }
  },
  // This function is run automaticaly by VUE framework
  created() {
    playground()
  },
  // methods: {
  //   testFunctionA() {
  //     console.log(this.text)
  //     console.log(this.someNumber)
  //     console.log(this.someObject.a)
  //     this.dataFunction()
  //     return 'I a test function A'
  //   }
  // }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
