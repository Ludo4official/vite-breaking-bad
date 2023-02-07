<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {

        name:'App',
        components: {

            AppHeader,
            AppMain,
            AppFooter

        },
        data() {
          return {
            characters: [],
            archetype: []
          }
        },
        created() {
          axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((response) => {
                this.characters = response.data.data
                console.log(response.data.data.slice(0,10))
        })
          axios
            .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
              this.archetype = response.data
              console.log(response.data.slice(0,10))
        });

    }
        
};
</script>

<template>
  
    <AppHeader></AppHeader>
    <AppMain :charactersList="characters" :charactersCount="characters.length" :archetypes="archetype"></AppMain>
    <AppFooter></AppFooter>
  
</template>

<style lang="scss">
@import './styles/partials/main.scss';
</style>
