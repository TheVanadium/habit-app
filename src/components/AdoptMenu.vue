<script>
    export default {
        name: "AdoptMenu",
        methods: {
        // send click information to parent
        closeAdoptMenu () {
            this.$emit("closeAdoptMenu")
            console.log("AdoptMenu Closed")
        }
    }
    }
</script>
<template>
    <div id="add-pet-menu">
        <div id="background" v-on:click=(closeAdoptMenu)>
            <div id="menu">

            </div>
        </div>
    </div>
</template>
<style>
/* background becomes unclickable and a translucent grey cover */
#background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 1;
    display: flex;
    justify-content: center;
    align-items: center;
}
/* menu is a white box with a border */
#menu {
    width: 500px;
    height: 300px;
    background-color: white;
    border: 1px solid black;
    z-index: 2;
}
</style>