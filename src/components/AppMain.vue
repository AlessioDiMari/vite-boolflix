<script>
import AppCard from './AppCard.vue'

export default{
    name: 'AppMain',

    data(){
        return{

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
            <AppCard></AppCard>
        </section>

        <section class="series">
            <h3>Series</h3>
            <AppCard></AppCard>
        </section>
    </div>
</template>



<style lang="scss">

.container-main{
    display: flex;
    flex-direction: column;
    gap: 36px;
    padding: 28px;
}

</style>