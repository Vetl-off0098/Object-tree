<template>
  <div id="app">
    <Node :obj="obj"/>
  </div>
</template>

<script>
import Node from './components/Node.vue'

export default {
  name: 'App',
  components: {
    Node
  },
  data () {
    return {
      obj: {
        a: {
          b: 'valueB'
        },
        c: 'valueC'
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
