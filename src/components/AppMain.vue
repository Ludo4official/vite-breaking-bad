<script>
import AppCard from './AppCard.vue'
export default {
    
    name: 'AppMain',
    components: {
        AppCard
    },
    props: {
        charactersList: {
            type: Array,
            default: []
        },
        charactersCount: {
            type: Number,
            default: 0
        },
        archetypes: {
            type: Array,
            default: []
        }
    }
    
}

</script>

<template>

<div class="my-cnt">

    <div class="container">
        <div class="row">
            <div class="col mt-3">

                <select class="form-select" aria-label="Default select example">
                    <option selected>Scegli un tipo...</option>
                    <option value="" v-for="archetype in archetypes">{{ archetype.archetype_name }}</option>
                </select>

            </div>
       </div>
    </div>

    <div class="container bg-light mt-3 rounded">

        <div class="row bg-dark rounded-top text-center py-3">

            <h3 class="text-light">Found {{ charactersCount }} cards</h3>
            
        </div>

        <div class="row">
            <div class="col-2" v-for="character in charactersList">
                <AppCard :character="character"></AppCard>
            </div>
        </div>
        
    </div>




</div>

</template>

<style lang="scss" scoped>

.my-cnt {
    background-color: goldenrod;
    
}


</style>