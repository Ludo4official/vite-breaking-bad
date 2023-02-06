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
            characters: []
          }
        },
        created() {
        axios
        .get('https://rickandmortyapi.com/api/character')
        .then((response) => {
            this.characters = response.data.results
        });

    }
        
};
</script>

<template>
  
    <AppHeader></AppHeader>
    <AppMain :charactersList="characters" :charactersCount="characters.length"></AppMain>
    <AppFooter></AppFooter>
  
</template>

<style lang="scss">
@import './styles/partials/main.scss';
</style>
