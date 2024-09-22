<script>
export default{
    data(){
        return{

        }
    },
    props:{
        playcard:{
            type : Object,
            required : true,
        }
    }
}
</script>

<template>
    <p>{{ playcard.name }}</p>
    <p>{{ playcard.archetype }}</p>
    <div class="card" style="width: 18rem;">
        <img :src="playcard.card_images[0].image_url" alt="">
        <div class="card-body">
            <h5>{{ playcard.name }}</h5>
            <p>{{ playcard.archetype }}</p>  
        </div>
    </div>
</template>

<style scoped>
</style>
