<script>
export default {
    name: "AdoptButton",
    methods: {
        // send click information to parent
        openAdoptMenu () {
            this.$emit("openAdoptMenu")
            console.log("AdoptButton clicked")
        }
    }
}
</script>
<template>
    <button v-on:click=(openAdoptMenu)  id="adopt-button">Add Pet</button>
</template>