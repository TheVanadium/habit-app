<script>
import PetPlace from './components/PetPlace.vue'

export default {
  name: 'App',
  data () {
    return {
      msg: 'Habit App!'
    }
  },
  components: {
    PetPlace
  }
}
</script>

<template>
  <div id="app">
      <p id="header">{{ msg }}!</p>
      <PetPlace></PetPlace>
    <router-view></router-view>
  </div>
</template>

<style>
:root {
  width: 100%;
  height: 100%;
}
#header {
  height: 10vh;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
#pet-place {
    height: 90vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>