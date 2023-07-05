<template>
    <div>
        <h2> {{ product.name }}</h2>
        <p class="color"> {{ formattedPrice(product.price) }}</p>
        <p v-if="product.available"> Available</p>
        <p v-else>Out of stock</p>
        <button @click="buy">Купить</button>

    </div>
</template>

<script>
export default {
    name: "ProductDetails",

    data() {
        return {
            product: {
                name: "prod1", price: 100, available: true
            },
            currency: '$',
        }
    },

    methods: {
        formattedPrice(price) {
            return this.currency.concat(price);
        },
        buy() {
            this.product.available = false;
        }
    }

}
</script>
<style lang="scss">
p,
h2 {
    font-size: 30px;
}

.color {
    color: red;
}
</style>