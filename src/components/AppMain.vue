<script>
import MainCardList from './MainCardList.vue';
import MainLoader from './MainLoader.vue';
import MainInput from './MainInput.vue';
import axios from "axios";

export default{
    data(){
        return{
            cardsList : [],
            apiUrl : "https://db.ygoprodeck.com/api/v7/cardinfo.php",
            loading : true,
        }
    },
    methods: {
        getCardsList(archetypeFilter = null){
            axios.get(this.apiUrl, {
                params: {
                    num : 500,
                    offset: 0,
                    archetype: archetypeFilter,
                }
            })
                .then((response) => {
                    // handle success
                    console.log(response.data.data);
                    this.cardsList = response.data.data;

                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
                .finally(() => {
                    this.loading = false;
                    // always executed
                });
        },
        changeCardList(information){
            console.log(`è arrivato ad AppMain ${information}`);
            this.getCardsList(information);
        }
    },
    created(){
        setTimeout(this.getCardsList, 2000);
    },
    components:{
        MainCardList,
        MainLoader,
        MainInput,
    }
}
</script>

<template>
    <MainInput @archetype-search="changeCardList"/>
    <MainLoader v-if="loading"/>
    <MainCardList v-else :cards="cardsList" />
</template>

<style lang="scss" scoped>
</style>
