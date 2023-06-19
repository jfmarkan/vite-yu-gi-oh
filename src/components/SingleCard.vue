<template>
    <article class="card mb-5 col-2 me-3 p-0">
        <img :src="image.image_url_small" class="w-100" :alt="name + ' image'">
        <div class="card-body text-center">
            <h5 class="card-title fw-bold">
                {{ name }}
            </h5>
            <p class="card-text">
                {{ archetype }}
            </p>
        </div>
    </article>
</template>

<script>
export default {
    name: 'SingleCard',
    data(){
        return {

        }
    },
    props:{
        name : String,
        archetype : String,
        image : String,
    },
}
</script>

<style lang="scss">
    
</style>