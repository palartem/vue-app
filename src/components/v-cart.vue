<template>
    <div class="v-cart">
        <router-link :to="{name: 'catalog'}">
            <div class="v-catalog__link">
                <i class="medium material-icons">shopping_cart</i>
                {{ CART.length }}
            </div>
            <button class="btn">Back to Catalog</button>
        </router-link>
        <h3 v-if="!CART.length">Корзина пустая</h3>
        <vCartItem
            v-for="(item, index) in CART"
            :key="item.article"
            :cart-item-data="item"
            @deleteFromCart="deleteFromCart(index)"
        />
    </div>
</template>
<script>
import vCartItem from './v-cart-item.vue';
import {mapActions, mapGetters} from "vuex";

export default {
    name: "v-cart",
    components: {
        vCartItem,
    },
    props: {
        cartData: {
            type: Object,
            default() {
                return [];
            },
        },
    },
    data() {
        return {};
    },
    computed: {
        ...mapGetters(['CART']),
    },
    methods: {
        ...mapActions(['DELETE_FROM_CART']),
        deleteFromCart(index) {
            this.DELETE_FROM_CART(index);
        }
    },
    watch: {},
    mounted() {

    },
};
</script>
<style scoped lang="scss">
.v-cart {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    color: gray;
    font-size: 20px;
    margin-bottom: 150px;
}

p {
    text-align: center;
    font-size: 26px;
}
</style>
