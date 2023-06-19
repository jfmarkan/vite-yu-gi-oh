<template>
    <div>
        <h3>CardsList</h3>
    </div>
    <SingleCard />
</template>

<script>
import SingleCard from './SingleCard.vue';

import axios from 'axios';



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
            console.log(response.data.results);
            setTimeout( () => {
                this.charactersList = response.data.results;
            }, 3000);
        })
        .catch(function (error) {
            console.log(error);
        })
    }
}
</script>

<style lang="scss">
    
</style>