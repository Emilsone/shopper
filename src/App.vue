<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <ShoppingList/>
  </div>
</template>

<script>
import ShoppingList from './components/ShoppingList.vue'

export default {
  name: 'App',
  components: {
   ShoppingList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
   background: #313131;
height: 100vh;

}
*{
padding:0px;
margin: 0px;
}
</style>
