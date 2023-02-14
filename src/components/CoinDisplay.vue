<script>
export default {
    data() {
        return {
            coins: 0,
        };
    },
}
</script>
<template>
    <div id="coin-display">
        <section id="coin-amount">
            <h1>{{this.coins}}</h1>
        </section>
        <section id="coin-icon">
            <img src="../assets/coin.png" alt="coin">
        </section>
        <section id="get-coins">
            <button @click="this.coins += 1">+</button>
        </section>
    </div>
</template>
<style>
#coin-display {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100px;
    height: 50px;
    background-color: #f5f5f5;
    border-radius: 10px;
    padding: 5px;
}
#coin-amount {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 50px;
    height: 50px;
    background-color: #f5f5f5;
    border-radius: 10px;
}
#coin-icon {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 50px;
    background-color: #f5f5f5;
    border-radius: 10px;
}
#coin-icon > img {
    width: 100%;
    height: 100%;
}
</style>