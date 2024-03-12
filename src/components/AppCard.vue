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
        },

        starRating(){
            return Math.ceil(this.movie.vote_average / 2);
        }
    }
}
</script>

<!-- {{ movie.vote_average }} -->

<template>
    <li class="card">
        <img :src="'http://image.tmdb.org/t/p/w342/' + movie.poster_path" alt="">
        <strong class="title">
            {{ movie.title ? movie.title : movie.name }}
        </strong>
        <div class="og-title">
            {{ movie.original_title ? movie.original_title : movie.original_name }}
        </div>
        <div class="lang">
            Lingua: 
            <img :src="getLanguageFlagUrl(movie.original_language)" :alt="movie.original_language">
        </div>
        <div class="rating">
            Voto: 
            <div  class="star">
                <i v-for="n in starRating()" class="fa-solid fa-star"></i>
            </div>
        </div>
    </li>
</template>



<style lang="scss">

.card{
    width: calc(100% / 5 - 24px / 5 * 4);

    > img{
        width: 100%;
        aspect-ratio: 2 / 3;
        object-fit: cover;
    }

    .lang{
        display: flex;
        align-items: center;
        gap: 8px;
    }

    .star{
        display: flex;
        flex-direction: row;
    }
}

</style>