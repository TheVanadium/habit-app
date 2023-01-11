<script>
import HabitPet from './HabitPet.vue'

export default {
    name: "PetPlace",
    data() {
        return {
            pets: [
                {id: 1, species: 'dog'},
                {id: 2, species: 'cat'},
                {id: 3, species: 'bird'},
                {id: 4, species: 'dog'},
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
        <HabitPet v-for="pet in this.pets" :key="pet.id" :species="pet.species"></HabitPet>
    </div>
</template>