<script>
import MainCardList from './MainCardList.vue';
import axios from "axios";

export default{
    data(){
        return{
              cardsList : [],
              apiUrl : "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",

        }
    },
    methods: {
        getCardsList(){
            axios.get(this.apiUrl)
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
        this.getCardsList();
    },
    components:{
        MainCardList,
    }
}
</script>

<template>
    <h2>io sono il main</h2>
    <MainCardList :cards="cardsList" />
</template>

<style lang="scss" scoped>
</style>
