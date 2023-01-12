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
    <div id="adopt-button">
        <button v-on:click=(openAdoptMenu)>Adopt</button>
    </div>
</template>