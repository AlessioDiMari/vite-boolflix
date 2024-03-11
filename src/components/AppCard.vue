<script>
export default{
    name: 'AppCard',

    props:{
        movie: Object,
    },

    methods: {
        getLanguageFlagUrl(languageCode) {
            switch (languageCode) {
                case 'en':
                    return 'https://flagcdn.com/w40/gb.png';
                case 'es':
                    return 'https://flagcdn.com/w40/es.png';
                case 'fr':
                    return 'https://flagcdn.com/w40/fr.png';
                case 'de':
                    return 'https://flagcdn.com/w40/de.png';
                case 'it':
                    return 'https://flagcdn.com/w40/it.png';
                default:
                    return 'https://flagcdn.com/w40/generic.png';
            }
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