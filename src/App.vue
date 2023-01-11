<script>
import PetPlace from './components/PetPlace.vue';
import AddPetButton from './components/AddPetButton.vue';
import AppHeader from './components/AppHeader.vue';

export default {
  name: 'App',
  components: {
    PetPlace,
    AddPetButton,
    AppHeader,
  }
}
</script>

<template>
  <div id="app">
    <AppHeader></AppHeader>
    <PetPlace></PetPlace>
    <AddPetButton></AddPetButton>
    <router-view></router-view>
  </div>
</template>

<style>
:root {
  margin: 0;
  width: 100vw;
  height: 100vh;
}
#header {
  height: 10vh;
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