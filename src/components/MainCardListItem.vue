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
    <div class="card mb-3" style="width: 18rem;">
        <img :src="playcard.card_images[0].image_url" alt="">
        <div class="card-body">
            <h5 class="text-white text-center">{{ playcard.name }}</h5>
            <p class="text-center">{{ playcard.archetype }}</p>  
        </div>
    </div>
</template>

<style scoped>
.card-body{
    background-color: goldenrod;
}

</style>
