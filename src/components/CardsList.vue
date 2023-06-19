<template>
    <div class="container">
        <div class="row py-3 px-5 justify-content-evenly">
            <SingleCard v-for="card in cardsList"
                :name="card.name"
                :archetype="card.archetype"
                :image="card.card_images[0].image_url"
            />
        </div>
    </div>
</template>

<script>
import SingleCard from './SingleCard.vue';

import axios from 'axios';
import {store} from '../store.js'


export default {
    name: 'CardsList',
    data(){
        return {
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
            cardsList : [],
            store
        }
    },
    components :{
        SingleCard,
    },
    created(){
        axios.get(this.apiUrl)
        .then( (response) => {
            console.log(response.data.data);
            this.cardsList = response.data.data;
        })
        .catch(function (error) {
            console.log(error);
        })
    }
}
</script>

<style lang="scss" scoped>
    .container{
        background-color: #FFF;
    }
</style>