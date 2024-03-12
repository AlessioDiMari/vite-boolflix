<script>
import AppCard from './AppCard.vue'
import { store } from '../store';

export default{
    name: 'AppMain',

    data(){
        return{
            store,
        }
    },
    components:{
        AppCard,
    }
}
</script>



<template>
    <div class="container-main">
        <section class="film">
            <h2>Film</h2>
            <ul>
                <AppCard v-for="actualMovie in store.movies"
                :movie="actualMovie"
                >
                </AppCard>
            </ul>
        </section>

        <section class="series">
            <h2>Series</h2>
            <ul>
                <AppCard v-for="actualSerie in store.series"
                :movie="actualSerie"
                >
                </AppCard>
            </ul>
        </section>
    </div>
</template>



<style lang="scss">

.container-main{
    display: flex;
    flex-direction: column;
    gap: 36px;
    padding: 28px;

    ul{
        list-style-type: none;
        display: flex;
        flex-wrap: wrap;
        gap: 24px;
    }
}

</style>