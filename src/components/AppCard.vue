<script>
export default{
    name: 'AppCard',

    props:{
        movie: Object,
    },

    methods: {
        getLanguageFlagUrl(languageCode) {
            // Costruisci l'URL della bandiera usando il codice della lingua
            return `https://flagcdn.com/w40/${languageCode.toLowerCase()}.png`;
        }
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
            Lingua: 
            <img :src="getLanguageFlagUrl(movie.original_language)" :alt="movie.original_language">
        </div>
        <div class="rating">
            Voto: {{ movie.vote_average }}
        </div>
    </li>
</template>



<style lang="scss">

.card{
    width: calc(100% / 5 - 24px / 5 * 4);

    .lang{
        display: flex;
        align-items: center;
        gap: 8px;
    }
}

</style>