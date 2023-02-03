<script>
import ShopItem from "./ShopItem.vue";
import CoinDisplay from "./CoinDisplay.vue";
export default {
    data () {
        return {

        }
    },
    components: {
        ShopItem,
        CoinDisplay
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
            <CoinDisplay></CoinDisplay>
        </div>
    </div>
</template>
<style>
#shop {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    margin: 0 5% 0 5%;
    position: relative;
}
.shop-row {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin: 5%;
}
/* absolutely position in the bottom right corner, 5% away from it */
#coin-display {
    position: absolute;
    bottom: 5rem;
    right: 5rem;
}
</style>