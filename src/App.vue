<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/hourglass.png" height="300" width="360">
    <HelloWorld msg="Welcome to Timer"/>
    <Timer />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Timer from './components/Timer.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Timer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f7f9fa;
  background-color: rgb(26, 7, 45);
  background-size: cover;
}
.logo {
  width: 100%;
  max-width: 360px;
  height: auto;
  margin: 0 auto 20px;
}

@media (max-width: 600px) {
  #app {
    padding: 10px;
  }
  
  .logo {
    max-width: 100%; 
    height: auto;
  }
}
</style>
