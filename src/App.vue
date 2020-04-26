<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SlideRanger
      :value="0"
      :steps="0"
      :min="0"
      :max="100"
      @onchange="log()"
    />
  </div>
</template>

<script>
import SlideRanger from "./components/SlideRanger";
export default {
  name: 'App',
  components: {
    SlideRanger
  },
   methods: {
    log() {
      console.log("Changed");
    }
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
