<template>
  <div id="app">
    <FilterItem/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Login from "./components/Login";
import FilterItem from "./components/FilterItem";

export default {
  name: 'App',
  components: {
    FilterItem,
    Login,
    HelloWorld
  }
}
</script>

<style>
</style>
