<template>
    <div class="v-cart-item">
        <img
            class="v-cart-item__img"
            :src="require('../assets/images/'+cartItemData.image)"
            alt="picture"
        >
        <div>
            <p>{{ cartItemData.name }}</p>
            <p>{{ cartItemData.price }}</p>
            <p>{{ cartItemData.article }}</p>
            <p>{{ cartItemData.about }}</p>
        </div>
        <div class="v-cart-item__quantity">
            <p>Quantity</p>
            <span>{{ cartItemData.quantity }}</span>
        </div>
        <button class="btn red" @click="deleteFromCart">Delete</button>
    </div>
</template>
<script>
export default {
    name: "v-cart-item",
    components: {},
    props: {
        cartItemData: {
            type: Object,
            default() {
                return {};
            },
        },
    },
    data() {
        return {};
    },
    computed: {},
    methods: {
        deleteFromCart() {
            this.$emit('deleteFromCart');
        },
    },
    watch: {},
    mounted() {

    },
};
</script>
<style lang="scss">
.v-cart-item {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-items: center;
    flex-basis: 25%;
    box-shadow: 0 0 8px gray;
    padding: 20px;
    margin: 20px;

    &__img {
        width: 160px
    }
}
</style>
