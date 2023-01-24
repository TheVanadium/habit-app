<script>
export default {
    name: "PetBowl",
    props: {
        id: Number,
        petName: String,
    },
    data: {
        isFull: true,
        bowlSrcFull: "/src/assets/bowl_full.jpg",
        bowlSrcEmpty: "/src/assets/bowl_empty.jpg",
    },
    computed: {
        bowlImageSrc() {
            return this.isFull ? this.bowlSrcFull : this.bowlSrcEmpty;
        }
    },
}
</script>
 <template>
    <div>
        <div class="pet-bowl" :id="this.id">
            <img v-on:click="this.petIsClean = !this.petIsClean" v-on:mouseenter="petMoveRandom" :src="petImageSrc" :alt="petImageAlt">
        </div>    
    </div>
 </template>

 <style>
    
 </style>