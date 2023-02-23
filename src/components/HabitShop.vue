<script>
import ShopItem from "./ShopItem.vue";
import CoinDisplay from "./CoinDisplay.vue";
export default {
    data() {
        return {
            coins: 0,
        };
    },
    methods: {
        itemBought() {
            this.coins -= 1000;
        },
        coinAdd() {
            this.coins += 1;
        }
    },
    components: {
        ShopItem,
        CoinDisplay,
    },
}
</script>
<template>
    <div>
        <div id="shop">
            <div class="shop-row" id="shop-row-1">
                <ShopItem @buy-item="itemBought" item="Scarf 1"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf 2"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
            </div>
            <div class="shop-row" id="shop-row-2">
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
                <ShopItem @buy-item="itemBought" item="Scarf"></ShopItem>
            </div>
            <CoinDisplay :coins="coins" @coinAdd="coinAdd"></CoinDisplay>
        </div>
    </div>
</template>
<style>
#shop {
    user-select: none;
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
