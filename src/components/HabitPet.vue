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
            petIsClean: true,
            moveDistance: 300,
            moveIntervalSeconds: 5,
            petImageAlt: this.species,
            petSrcClean: "/src/assets/pets/habit_" + this.species + ".jpg",
            petSrcDirty: "/src/assets/pets/habit_" + this.species + "_dirty.jpg",
        }
    },
    methods: {
        randomlyGenerateMoveDistance() {
            return Math.floor(Math.random() * this.moveDistance * 2) - this.moveDistance;
        },
        movePetTo(pet, x, y) {
            pet.style.transform = "translate(" + x + "px, " + y + "px)";
            pet.style.transition = "transform 1s";
        },
        petMoveRandom() {
            let petMoved=false;
            var pet = document.getElementById(this.id);
            var rect = pet.getBoundingClientRect();
            var currentX = rect.left;
            var currentY = rect.top;

            while(!petMoved) {
                var x = this.randomlyGenerateMoveDistance()
                var y = this.randomlyGenerateMoveDistance()

                let petRemainsInScreen = currentX + x > 0 && currentX + x < window.innerWidth - 50 && currentY + y > 0 && currentY + y < window.innerHeight - 50;
                if (petRemainsInScreen) {
                    this.movePetTo(pet, x, y);
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
        },
        petImageSrc() {
            return this.petIsClean ? this.petSrcClean : this.petSrcDirty;
        }
    },
    mounted() {
        setInterval(this.petMoveRandom, Math.floor(Math.random() * 10000) + (this.moveIntervalSeconds*1000));
    }
}
</script>

<template>
    <div class="habit-pet" :id="this.id">
        <img v-on:click="this.petIsClean = !this.petIsClean" v-on:mouseenter="petMoveRandom" :src="petImageSrc" :alt="petImageAlt">
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