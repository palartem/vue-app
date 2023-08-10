<template>
    <div class="v-main-wrapper">
        <router-view></router-view>
    </div>
</template>
<script>
import {mapGetters} from 'vuex';

export default {
    name: "v-main-wrapper",
    components: {
        // vCatalog,
        // vCart,
    },
    props: {
        testProps: {
            type: String,
            default: '',
        },
    },
    data() {
        return {
            title: 'Hello World',
        };
    },
    computed: {
        ...mapGetters(['CART']),
    },
    methods: {},
    watch: {},
    mounted() {
    },
};
</script>
<style lang="scss">
.v-main-wrapper {
    max-width: 900px;
    margin: 0 auto;
    padding: 20px 0px;
}
</style>
