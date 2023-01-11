<script>
export default {
    name: "HabitPet",
    props : {
        species : String,
    },
    data () {
        return {  
            petImageInfo : {
                src: "/src/assets/habit_" + this.species + ".jpg",
                alt: this.species
            },
            petIsClean: true
        }
    },
    methods: {
        togglePetGroomState() {
            this.petIsClean = !this.petIsClean
            if (this.petIsClean) {
                this.petImageInfo.src = "/src/assets/habit_" + this.species + ".jpg"
            } else {
                this.petImageInfo.src = "/src/assets/habit_" + this.species + "_dirty.jpg"
            }
        }
    },
    computed: {
        petInfo() {
            switch(this.species) {
                case 'dog':
                    return {
                        sound: 'woof'
                    }
                case 'cat':
                    return {
                        sound: 'meow'
                    }
                case 'bird':
                    return {
                        sound: 'tweet'
                    }
                default:
                    return {
                        sound: "sound of invalid species"
                    }
            }
        }
    }
}
</script>

<template>
    <img v-on:click="togglePetGroomState()" :src="petImageInfo.src" :alt="petImageInfo.alt" class="habit-pet">
</template>

<style>
.habit-pet {
    width: 100px;
    height: 100px;
}
</style>