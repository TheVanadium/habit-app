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
<style>
    #adopt-button {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>