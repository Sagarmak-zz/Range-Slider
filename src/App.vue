<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SlideRangeWrapper />
  </div>
</template>

<script>
import SlideRangeWrapper from "./components/SlideRangeWrapper";
export default {
  name: 'App',
  components: {
    SlideRangeWrapper
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
