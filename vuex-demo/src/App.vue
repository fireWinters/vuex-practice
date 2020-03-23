<template>
  <div id="app">
    <!-- {{this.$store.state.count}} -->
    {{count}}
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="countIncr">点我增加</button>
    <button @click="countBignumber">增加固定数</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  computed:{
    count(){
      return this.$store.state.count
    }
  },
  methods:{
    countIncr(){
      this.$store.commit('countIncrease')
    },
    countBignumber(){
      const na = 200
      this.$store.commit('countNumber',na)
    }
  }
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
