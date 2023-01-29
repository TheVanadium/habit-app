<script>
import ShopItem from "./ShopItem.vue";
export default {
    data () {
        return {

        }
    },
    components: {
        ShopItem
    },
}
</script>
<template>
    <div>
        <div id="shop">
            <div class="shop-row" id="shop-row-1">
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
            </div>
            <div class="shop-row" id="shop-row-2">
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
                <ShopItem item="Scarf"></ShopItem>
            </div>
        </div>
    </div>
</template>
<style>
#shop {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin: 0 5% 0 5%;
}
.shop-row {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin: 5%;
}
</style>