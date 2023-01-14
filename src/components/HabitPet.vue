<script> 
export default {
    name: "HabitPet",
    props : {
        species : String,
        habit : String,
        id : Number,
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
        },
        petMoveRandom() {
            let petMoved=false;
            var pet = document.getElementById(this.id);
            var rect = pet.getBoundingClientRect();
            var currentX = rect.left;
            var currentY = rect.top;

            // translate with transition only if the pet is not out of the screen, otherwise reroll and try again
            while(!petMoved) {
                // randomly generate x and y
                var x = Math.floor(Math.random() * 100) - 50;
                var y = Math.floor(Math.random() * 100) - 50;
                console.log("Move attempt: " + x + ", " + y);
                if (currentX + x > 0 && currentX + x < window.innerWidth - 50 && currentY + y > 0 && currentY + y < window.innerHeight - 50) {
                    pet.style.transform = "translate(" + x + "px, " + y + "px)";
                    pet.style.transition = "transform 1s";
                    petMoved = true;
                }
            }
        },
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
    <div class="habit-pet" :id="this.id">
        <img v-on:click="togglePetGroomState()" v-on:mouseenter="petMoveRandom()" :src="petImageInfo.src" :alt="petImageInfo.alt">
    </div>
</template>

<style>
.habit-pet {
    width: 50px;
    height: 50px;
}
.habit-pet img {
    width: 50px;
    height: 50px;
}
.habit-description {
    text-align: center;
}
</style>