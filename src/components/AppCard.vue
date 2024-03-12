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
    <li>
        <div class="card">
            <div class="card-front" :style="{ backgroundImage: 'url(http://image.tmdb.org/t/p/w342/' + movie.poster_path + ')' }">
            </div>
            <div class="card-back">
                <strong class="title">
                    {{ movie.title ? movie.title : movie.name }}
                </strong>
                <div class="og-title">
                    {{ movie.original_title ? movie.original_title : movie.original_name }}
                </div>
                <div class="overview">
                    Trama:
                    <div class="overview">{{ movie.overview }}</div> 
                    <!-- <img :src="getLanguageFlagUrl(movie.original_language)" :alt="movie.original_language"> -->
                </div>
                <div class="rating">
                    Voto: 
                    <div class="star">
                        <i v-for="n in 5" class="fa-solid fa-star" :class="{ 'yellow-star': n <= starRating() }"></i>
                    </div>
                </div>
            </div>
        </div>
    </li>
</template>



<style lang="scss">

li{
    width: calc(100% / 5 - 24px / 5 * 4);

}

li:hover > .card{
    transform: rotateY(180deg);
}

.card{
    position: relative;
    aspect-ratio: 2 / 3;
    transition: transform 1000ms;
    transform-style: preserve-3d;
}



.card-front{
    position: absolute;
    width: 100%;
    aspect-ratio: 2 / 3;
    background-size: cover;
    background-position: center;
    backface-visibility: hidden;
}

.card-back{
    padding: 10px;
    position: absolute;
    width: 100%;
    aspect-ratio: 2 / 3;
    background-color: black;
    transform: rotateY(180deg);
    backface-visibility: hidden;
    overflow-y: auto;

    strong{
        font-size: 1.1em;
    }
    .og-title{
        font-size: 0.9em;
    }
}

.overview{
    display: flex;
    gap: 6px;
}

.rating{
    display: flex;
    align-items: center;
    gap: 6px;
    .star{
        display: flex;
        flex-direction: row;
    
        .yellow-star{
            color: yellow;
        }
    }
}


</style>