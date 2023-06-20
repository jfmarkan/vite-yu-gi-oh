<template>
    <main>
        <div class="background">
            <div class="container">
                <ActionBar />
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
    created(){
        axios.get(this.apiUrl)
        .then( (response) => {
            console.log(response.data.data);
            this.cardsList = response.data.data;
            this.store.isLoading = false
        })
        .catch(function (error) {
            console.log(error);
        })
    },
}
</script>

<style lang="scss">
    .background{
        background-color: #d48f38;
    }
</style>