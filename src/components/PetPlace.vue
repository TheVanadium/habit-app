<script>
import HabitPet from './HabitPet.vue'

export default {
    name: "PetPlace",
    components: {
        HabitPet
    }
}
</script>
<template>
    <div id="pet-place">
        <HabitPet species="bird"></HabitPet>
        <HabitPet species="cat"></HabitPet>
        <HabitPet species="dog"></HabitPet>
    </div>
</template>