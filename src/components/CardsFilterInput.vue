<template lang="">
    <div>
        <form action="">
            <select name="cards-race" id="cards-race" v-model="selector">
                <option value="Aqua">
                    Aqua
                </option>
                <option value="Beast">
                    Beast
                </option>
                <option value="Beast-Warrior">
                    Beast-Warrior
                </option>
                <option value="Creator-God">
                    Creator-God
                </option>
                <option value="Cyberse">
                    Cyberse
                </option>
                <option value="Dinosaur">
                    Dinosaur
                </option>
                <option value="Divine-Beast">
                    Divine-Beast
                </option>
                <option value="Dragon">
                    Dragon
                </option>
                <option value="Fairy">
                    Fairy
                </option>
                <option value="Fiend">
                    Fiend
                </option>
                <option value="Fish">
                    Fish
                </option>
                <option value="Insect">
                    Insect
                </option>
                <option value="Machine">
                    Machine
                </option>
                <option value="Plant">
                    Plant
                </option>
                <option value="Psychic">
                    Psychic
                </option>
                <option value="Pyro">
                    Pyro
                </option>
                <option value="Reptile">
                    Reptile
                </option>
                <option value="Rock">
                    Rock
                </option>
                <option value="Sea Serpent">
                    Sea Serpent
                </option>
                <option value="Spellcaster">
                    Spellcaster
                </option>
                <option value="Thunder">
                    Thunder
                </option>
                <option value="Warriro">
                    Warrior
                </option>
                <option value="Winged Beast">
                    Winged Beast
                </option>
                <option value="Wyrm">
                    Wyrm
                </option>
                <option value="Zombie">
                    Zombie
                </option>
            </select>
        </form>
    </div>
</template>
<script>
import axios from 'axios';
import { cardsList } from '../js/cardsList.js';

export default {
    name: "CardsFilterInput",
    data() {
        return {
            selector: "Zombie",
            cardsList,
        }
    },
    methods: {
        axiosCardsFunc(raceName="Zombie"){
            return axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&race=${raceName}`)
            .then(resp => {
                this.cardsList.cards= resp.data.data;
                console.log(this.cardsList)
            })
            .catch(err => console.warn(err))
        }
    },
    created() {
        this.axiosCardsFunc();
    },
    updated() {
        this.axiosCardsFunc(this.selector);
    }
}
</script>
<style lang="scss">
    @use "../style/general.scss"
</style>