<script>
export default {
    name: "ShopItem",
    props: {
        item: {
            type: String,
            required: true
        }
    },
    data() {
        return {
        }
    },
    methods: {
        buyItem() {
            this.$emit('buy-item', this.item);
        }
    },
    
}
</script>
<template>
    <div class="item-card">
        <section class="card-main-content">
            <img :alt=item>
        </section>
        <section class="card-footer" v-on:click=(buyItem)>
            <p class="card-footer-price">1000</p>
            <img src="src\assets\coin.png" class="coin-image">
        </section>
    </div>
</template>
<style>
.coin-image {
    width: 20px;
    height: 20px;
}
.item-card {
    width: 112.5px;
    height: 150px;
    border: 1px solid black;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
.card-main-content {
    flex: 5;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background-color: #D9D9D9;
    border-radius: 10px 10px 0 0;
}
.card-footer {
    flex: 1;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background-color: #F1ECEC;
    border-radius: 0 0 10px 10px;
}
.card-footer:hover {
    cursor: default;
    background-color: #E6E6E6;
}
</style>