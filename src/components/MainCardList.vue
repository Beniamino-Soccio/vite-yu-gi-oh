<script>
import MainCardListItem from './MainCardListItem.vue';

export default{
    data(){
        return{

        }
    },
    props:{
        cards:{
            type: Array,
            required: true,
        }
    },
    components:{
      MainCardListItem

    }
}
</script>

<template>
    <div class="row">
        <p class="text-white text-center fs-1">found {{  cards.length }} cards</p>
        <div class="col d-flex justify-content-evenly flex-wrap bg-white py-5">
            <MainCardListItem v-for="card in cards" 
                :key="card.id"
                :playcard="card"
            />
        </div>
    </div>
    
</template>

<style lang="scss" scoped>

</style>
