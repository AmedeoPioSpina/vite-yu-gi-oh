<template lang="">
    <div>
        <ul class="d-flex flex-wrap justify-content-center">
            <CardBase v-for="card in cardsList" :key="card.id" :cardInfo="card"/>
        </ul>
    </div>
</template>
<script>
import CardBase from './CardBase.vue';

export default {
    name: "CardsContainer",
    components: {
        CardBase,
    },
    props: [
        "cardsList"
    ],
    data() {
        return {
            
        }
    },
}
</script>
<style lang="scss">
    @use "../style/general.scss" as *;
</style>