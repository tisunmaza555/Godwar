<template>
  <div id="app">
    <img src="https://hunnywhoarei.files.wordpress.com/2016/01/e0b8abe0b899e0b989e0b8b2e0b89be0b881e0b8a3e0b8b2e0b8a1e0b980e0b881e0b8b5e0b8a2e0b8a3e0b895e0b8b4e0b98ce0b8a5e0b988e0b8b2e0b8aae0b8b8.jpg" alt width="100%"  >
  
    <war01/>
  </div>
</template>

<script>
import war01 from './components/war01.vue'

export default {
  name: 'App',
  components: {
    war01
  }
}
</script>

<style>
#app {
  background-image: url(https://pbs.twimg.com/media/EIsOLchU8AA9hGl.jpg);
  background-size: cover;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
