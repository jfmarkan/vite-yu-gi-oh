<template>
    <div class="container py-3">
        <select name="type" id="type-select" >
            <option v-for="filter in filtersList" :value="filter.archetype_name">{{filter.archetype_name}}</option>
        </select>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'ActionBar',
    data(){
        return {
            filterUrl : 'https://db.ygoprodeck.com/api/v7/archetypes.php',
            filtersList:[],
        }
    },
    created(){
        axios.get(this.filterUrl)
            .then((response) => {
                this.filtersList = response.data;
            })
            .catch(function (error) {
                console.log(error);
            })
        },
    };
</script>

<style lang="scss">
    
</style>