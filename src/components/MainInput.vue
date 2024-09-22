<script>
import axios from "axios";
export default{
    data(){
        return{
            selecteditem: "",
            archetypes: [],
            apiUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",

        }
    },
    methods: {
        getArchetypesList(){
            axios.get(this.apiUrl)
                .then((response) => {
                    // handle success
                    console.log(response.data);
                    this.archetypes = response.data;

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
        logMessage(message){
            console.log(`chiamata log message con ${message}`);
            this.$emit("archetypeSearch", message);
        }
    },
    created(){
        this.getArchetypesList();
    },
}
</script>

<template>
    <div class="form-input-group">
        <select class="form-select" v-model="selectedItem" @change="logMessage(selectedItem)">
            <option v-for="(archetype, index) in archetypes" :key=index :value="archetype.archetype_name"> {{ archetype.archetype_name }}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
div{
    padding-top: 50px;
}
</style>