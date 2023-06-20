<template>
    <div>
        <p>Found {{cardsList.length}} Cards</p>
    </div>
</template>

<script>
import {store} from '../store.js'

    export default {
        name: 'ResultCounter',
        data(){
            return{
                store
            }
        },
        props:{
            cardsList: Array,
        },
    }
</script>

<style lang="scss" scoped>
    div{
        background-color: #212529;


        p{
            color: #FFF;
            font-weight: bold;
            font-size: .9rem;
        }
    }
</style>