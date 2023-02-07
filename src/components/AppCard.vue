<script>

export default {
    
    name: 'AppCard',
    props: {
        character: Object
    }
   
}

</script>

<template>


<div class="card text-center my-3">
    <img src="https://picsum.photos/200/300" class="card-img-top" :alt="character.name">
    <div class="card-body">
        <h5 class="card-title text-light">{{ character.name }}</h5>
        <p class="card-text fw-bolder">{{ character.archetype }}</p>
        <div class="fst-italic">{{ character.type }}</div>
    </div>
</div>


</template>

<style lang="scss" scoped>

.card {
    background-color: goldenrod;
}

</style>
