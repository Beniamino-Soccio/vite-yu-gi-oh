<script>
import AppHeader from "./components/AppHeader.vue"
import AppMain from "./components/AppMain.vue"
export default{
    data(){
        return{

        }
    },
    components:{
      AppHeader,
      AppMain,

    }
}
</script>

<template>
    <AppHeader/>
    <div class="main-content">
        <div class="container">
            <AppMain/>
        </div> 
    </div>
    
</template>

<style lang="scss">
@use "bootstrap/scss/bootstrap.scss";
@use "./style/general.scss";
.main-content{
    background-color: goldenrod;
}
</style>
