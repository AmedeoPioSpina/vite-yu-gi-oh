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
import axios from 'axios';

export default {
    name: "AppMain",
    components: {
        CardsFilterInput,
        CardsContainer
    },
    data() {
        return {
            
        }
    },
    methods: {
        axiosCardsFunc(){
            return axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
            .then(resp => resp.data.data)
            .catch(err => console.warn(err))
        }
    },
    created() {
        this.axiosCardsFunc();
    }
}
</script>
<style lang="scss">
    @use "../style/general.scss" as *;
</style>