<template>
  <div id="app">
    <Cart />
  </div>
</template>

<script>
import Cart from './components/Cart'

export default {
  name: 'App',
  components: {
    Cart
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
