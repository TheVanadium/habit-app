<script>
    export default {
        methods: {
            goToShop() {
                this.$emit("goToShop", "Shop")
            },
            goToPets() {
                this.$emit("goToPets", "Pets")
            },
        }
    }
</script>
<template>
    <div id="navigation">
        <p v-on:click="goToPets">Pets</p>
        <p v-on:click="goToShop">Shop</p>
    </div>
</template>
<style>
    #navigation {
        display: flex;
        align-items: center;
    }
    #navigation p {
        padding-left: 5px;
        padding-right: 5px;
    }
    #navigation p:hover {
        text-decoration: underline;
        cursor: pointer;
    }
</style>