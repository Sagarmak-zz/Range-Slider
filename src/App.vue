<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SliderWrapper />
  </div>
</template>

<script>
import SliderWrapper from "./components/SliderWrapper";
export default {
  name: 'App',
  components: {
    SliderWrapper
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  background: #2c3782;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 1rem;
}
</style>
