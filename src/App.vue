<script>
import TheHeader from "./components/TheHeader.vue"
import TheMain from "./components/TheMain.vue"
import TheFooter from "./components/TheFooter.vue"


export default {
    components: { TheHeader, TheMain, TheFooter, },

    data() {
        return {

        };
    },
    methods: {},

    beforeMount() { },
}
</script>


<template>
    <div class="">
        <div>
            <TheHeader></TheHeader>
        </div>
        <div>
            <TheMain></TheMain>
        </div>
        <div>
            <TheFooter></TheFooter>
        </div>
    </div>

</template>

<style lang="scss">
@use "./styles/general.scss";
</style>

