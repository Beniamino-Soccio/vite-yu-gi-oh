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
        <div class="col d-flex justify-content-evenly flex-wrap bg-white mt-5 py-5">
            <MainCardListItem v-for="card in cards" 
                :key="card.id"
                :playcard="card"
            />
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
</style>
