<template>
    <div class="container">
        <div class="row" v-if="store.isLoading">
            <div class="col-12">
                <AppLoader />
            </div>
        </div>
        <div class="row py-3 px-5 justify-content-evenly" v-else>
            <ResultCounter />
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
import ResultCounter from './ResultCounter.vue';
import AppLoader from './AppLoader.vue';
import axios from 'axios';
import {store} from '../store.js'


export default {
    name: 'CardsList',
    data(){
        return {
            store
        }
    },
    props:{
        cardsList: Array,
    },
    components :{
        SingleCard,
        ResultCounter,
        AppLoader
    },
    
}
</script>

<style lang="scss" scoped>
    .container{
        background-color: #FFF;
    }
</style>