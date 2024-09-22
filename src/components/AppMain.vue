<script>
import MainCardList from './MainCardList.vue';
import axios from "axios";

export default{
    data(){
        return{
              cardsList : [],
              apiUrl : "https://db.ygoprodeck.com/api/v7/cardinfo.php",

        }
    },
    methods: {
        getCardsList(numOfCards){
            axios.get(this.apiUrl, {
                params: {
                    num : numOfCards,
                    offset: 0,
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
                .finally(function () {
                    // always executed
                });
        }
    },
    created(){
        this.getCardsList(40);
    },
    components:{
        MainCardList,
    }
}
</script>

<template>
    <MainCardList :cards="cardsList" />
</template>

<style lang="scss" scoped>
</style>
