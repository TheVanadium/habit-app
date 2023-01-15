<script>
import HabitPet from './HabitPet.vue'

export default {
    name: "PetPlace",
    data() {
        return {
            pets: [
                {id: 1, species: 'dog', habit: 'Brush Teeth'},
                {id: 2, species: 'cat', habit: 'Shower'},
                {id: 3, species: 'bird', habit: 'Jog'},
                {id: 4, species: 'dog', habit: 'Practice Instrument'},
            ],
        };
    },
    components: {
        HabitPet
    }
}
</script>
<template>
    <div id="pet-place">
        <div id="petPlaceBackground">
            <div id="house"></div>
            <div id="grass"></div>
            <div id="sidewalk"></div>
            <div id="road"></div>
        </div>
        <div id="pet-lineup-area">
            <HabitPet v-for="pet in this.pets" :key="pet.id" :species="pet.species" :habit="pet.habit" :id="pet.id"></HabitPet>
        </div>
    </div>
</template>
<style>
#pet-lineup-area {
    top: 47%;
    margin: 0;
    position: absolute;
    width: 100%;
    height: 50px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
#petPlaceBackground {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: center;
}
#petPlaceBackground > div {
    height: 100%;
}
#house {
    flex: 1;
    background-color: #8B4513;
}
#grass {
    flex: 6;
    background-color: #03BF1D;
}
#sidewalk {
    flex: 1;
    background-color: #D3D3D3;
}
#road {
    flex: 1;
    background-color: #808080;
}
</style>