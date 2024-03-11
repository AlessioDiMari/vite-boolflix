<script>
export default{
    name: 'AppCard',

    props:{
        movie: Object,
    }
}
</script>



<template>
    <li class="card">
        <strong class="title">
            {{ movie.title }}
        </strong>
        <div class="og-title">
            {{ movie.original_title }}
        </div>
        <div class="lang">
            Lingua: {{ movie.original_language }}
        </div>
        <div class="rating">
            Voto: {{ movie.vote_average }}
        </div>
    </li>
</template>



<style lang="scss">

.card{
    width: calc(100% / 5 - 24px / 5 * 4);
}

</style>