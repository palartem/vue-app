<template>
    <div class="v-catalog">
        <router-link :to="{name: 'cart', params: { CART }}">
            <div class="v-catalog__link">
                <i class="medium material-icons">shopping_cart</i>
                {{ CART.length }}
            </div>
        </router-link>
        <div class="v-catalog__list">
            <vCatalogItem
                v-for="product in PRODUCTS"
                :key="product.article"
                :product-data="product"
                @addToCart="addToCart"
            />
        </div>
    </div>
</template>
<script>
import vCatalogItem from './v-catalog-item.vue';
import {mapActions, mapGetters} from 'vuex';

export default {
    name: "v-catalog",
    components: {
        vCatalogItem,
    },
    props: {},
    data() {
        return {};
    },
    computed: {
        ...mapGetters(['PRODUCTS', 'CART']),
    },
    methods: {
        ...mapActions(['GET_PRODUCTS_FROM_API', 'ADD_TO_CART']),
        addToCart(data) {
            this.ADD_TO_CART(data);
        },
    },
    watch: {},
    mounted() {
        this.GET_PRODUCTS_FROM_API().then((response) => {
            if (response.data) {
                console.log('Данные пришли');
            }
        });
    },
};
</script>
<style lang="scss">
.v-catalog{
    color: gray;
    font-size: 20px;
}
.v-catalog,
.v-catalog__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
}

.v-catalog__link {
}
</style>
