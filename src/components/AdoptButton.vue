<script>
export default {
    name: "AdoptButton",
    methods: {
        // send click information to parent
        openAdoptMenu () {
            this.$emit("openAdoptMenu")
        }
    }
}
</script>
<template>
    <div id="adopt-button">
        <button v-on:click=(openAdoptMenu)>Adopt</button>
    </div>
</template>