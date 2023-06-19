<template>
    <div>
        <h2>Main</h2>
    </div>
    <ActionBar />
    <CardsList />
</template>

<script>
import CardsList from './CardsList.vue';
import ActionBar from './ActionBar.vue';

export default {
    name: 'AppMain',
    data(){
        return {

        }
    },
    components:{
        CardsList,
        ActionBar
    }
}
</script>

<style lang="scss">
    
</style>