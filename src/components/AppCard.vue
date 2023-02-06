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
    <img src="..." class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">{{ character.name}}</h5>
        <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    </div>
</div>


</template>

<style lang="scss" scoped>

.card {
    background-color: goldenrod;
}

</style>
