<template lang="">
    <main>
        <section>
            <CardsFilterInput @cardsInfoList="moveDataFunc"/>
            <CardsContainer :cardsList="cardsInfoList"/>
        </section>
    </main>
</template>
<script>
import CardsFilterInput from './CardsFilterInput.vue';
import CardsContainer from './CardsContainer.vue';

export default {
    name: "AppMain",
    components: {
        CardsFilterInput,
        CardsContainer
    },
    data() {
        return {
            cardsInfoList: [],
        }
    },
    methods: {
        moveDataFunc( list ){
            this.cardsInfoList = list;
        }
    },
}
</script>
<style lang="scss">
    @use "../style/general.scss" as *;
</style>