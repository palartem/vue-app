<template>
    <vMainWrapper/>
</template>
<script>
import vMainWrapper from './components/v-main-wrapper.vue'
export default {
    name: "app",
    components: {
        vMainWrapper
    },
    props: {},
    data() {
        return {
        };
    },
    computed: {},
    methods: {},
    watch: {},
    mounted() {

    },
};
</script>

<style lang="scss">
@import "~materialize-css/dist/css/materialize.css";
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

</style>
