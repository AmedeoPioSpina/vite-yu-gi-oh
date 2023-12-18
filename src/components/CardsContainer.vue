<template lang="">
    <div>
        <ul class="d-flex flex-wrap justify-content-center">
            <CardBase v-for="card in cardsList.cards" :key="card.id" :cardInfo="card"/>
        </ul>
    </div>
</template>
<script>
import CardBase from './CardBase.vue';
import { cardsList } from '../js/cardsList';

export default {
    name: "CardsContainer",
    components: {
        CardBase,
    },
    data() {
        return {
            cardsList
        }
    },
}
</script>
<style lang="scss">
    @use "../style/general.scss" as *;
</style>