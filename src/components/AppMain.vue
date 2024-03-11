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
            <h3>Film</h3>
            <ul>
                <AppCard v-for="actualMovie in store.movies"
                :movie="actualMovie"
                >
                
                </AppCard>
            </ul>
        </section>

        <!-- <section class="series">
            <h3>Series</h3>
            <AppCard></AppCard>
        </section> -->
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