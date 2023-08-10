<template>
    <div class="v-catalog-item">
        <img
            class="v-catalog-item__img"
            :src="require('../assets/images/'+productData.image)"
            alt="picture"
        >
        <p
            class="v-catalog-item__name"
        >
            {{ productData.name }}
        </p>
        <p
            class="v-catalog-item__price"
        >
            {{ productData.price }}
        </p>
        <button
            class="v-catalog-item__btn btn"
            @click="addToCart"
        >
            add
        </button>
    </div>
</template>
<script>
export default {
    name: "v-catalog-item",
    components: {},
    props: {
        productData: {
            type: Object,
            default() {
                return {}
            },
        },
    },
    data() {
        return {};
    },
    computed: {},
    methods: {
        addToCart() {
            this.$emit('addToCart', this.productData);
        },
    },
    watch: {},
    mounted() {

    },
};
</script>
<style lang="scss">
.v-catalog-item {
    flex-basis: 40%;
    box-shadow: 0 0 8px gray;
    padding: 20px;
    margin: 20px;
}
.v-catalog-item__img{
    width: 160px;
    margin: 0  auto;
    display: block;
}
</style>
