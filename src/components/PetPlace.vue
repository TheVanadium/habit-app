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
        <HabitPet v-for="pet in this.pets" :key="pet.id" :species="pet.species" :habit="pet.habit"></HabitPet>
    </div>
</template>