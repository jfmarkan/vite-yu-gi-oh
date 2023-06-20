<template>
    <main>
        <div class="background">
            <div class="container">
                <ActionBar @filtered="filteredCards"/>
                <CardsList :cardsList="cardsList"/>
            </div>
        </div>
    </main>
</template>

<script>
import CardsList from './CardsList.vue';
import ActionBar from './ActionBar.vue';
import axios from 'axios';
import {store} from '../store.js'


export default {
    name: 'AppMain',
    data(){
        return {
            store,
            cardsList:[],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
        }
    },
    components:{
        CardsList,
        ActionBar,
    },
    methods: {
        filteredCards(filterApplied = ""){
            axios.get(this.apiUrl, {
                params: {
                    archetype: filterApplied
                }
            })
            .then( (response) => {
            this.cardsList = response.data.data;
            this.store.isLoading = false
            })
            .catch(function (error) {
            console.log(error);
            })
        }    
    },
    created(){
        this.filteredCards();
    },
}
</script>

<style lang="scss">
    main{
        min-height: 94vh;

        .background{
            background-color: #d48f38;
            height: 100%;
            padding-bottom: 4rem;
        }
    }
</style>