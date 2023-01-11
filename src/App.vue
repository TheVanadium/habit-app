<script>
import PetPlace from './components/PetPlace.vue';
import AddPetButton from './components/AddPetButton.vue';

export default {
  name: 'App',
  data () {
    return {
      msg: 'Habit App!'
    }
  },
  components: {
    PetPlace,
    AddPetButton,
  }
}
</script>

<template>
  <div id="app">
      <p id="header">{{ msg }}!</p>
      <PetPlace></PetPlace>
      <AddPetButton></AddPetButton>
    <router-view></router-view>
  </div>
</template>

<style>
:root {
  width: 100vw;
  height: 100vh;
}
#header {
  height: 10vh;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
#pet-place {
  height: 80vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
#add-pet-button {
  height: 10vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>