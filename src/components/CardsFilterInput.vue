<template lang="">
    <div>
        <form action="">
            <select name="cards-race" id="cards-race" v-model="selector" @change="axiosCardsFunc(cardsUrl += selector)">
                <option v-for="(item, index) in archetypeList" :key="index" :value="item.archetype_name">
                    {{ item.archetype_name }}
                </option>
            </select>
        </form>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    name: "CardsFilterInput",
    data() {
        return {
            archetypeList: [],
            selector: "",
            cardsUrl: `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=`,
            cardsList: []
        }
    },
    methods: {
        axiosCardsFunc(url="https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"){
            return axios.get(url)
            .then(resp => {
                this.cardsList= [...resp.data.data];
                console.log(this.cardsList);
                this.$emit("cardsInfoList", this.cardsList);
            })
            .catch(err => console.warn(err))
        },
        axiosArchetypeFunc(){
            return axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php")
            .then(resp => {
                this.archetypeList= [...resp.data];
                console.log(this.archetypeList);
            })
            .catch(err => console.warn(err))
        }
    },
    created() {
        this.axiosCardsFunc();
        this.axiosArchetypeFunc();
    },
}
</script>
<style lang="scss">
    @use "../style/general.scss"
</style>