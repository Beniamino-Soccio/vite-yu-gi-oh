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
    <h3>io sono la card list e {{  cards.length }} elementi</h3>
    <MainCardListItem v-for="card in cards" 
        :key="card.id"
        :playcard="card"
    />
</template>

<style lang="scss" scoped>
</style>
