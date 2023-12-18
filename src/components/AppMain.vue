<template lang="">
    <main>
        <section>
            <CardsFilterInput />
            <CardsContainer />
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
        }
    }
}
</script>
<style lang="scss">
    @use "../style/general.scss" as *;
</style>