<template>
    <main>
        <div class="background">
            <div class="container">
                <ActionBar />
                <CardsList />
            </div>
        </div>
    </main>
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
    .background{
        background-color: #d48f38;
    }
</style>