<script>
import { store } from '../store';

export default{
    name: 'AppHeader',

    data(){
        return{
            store
        }
    }
}
</script>



<template>
    <div class="container">
        <h1 class="site-name">
            boolflix
        </h1>
        <div class="search">
            <input type="search" v-model="store.searchText">
            <button @click="$emit('search')">
                Cerca
            </button>
        </div>
    </div>
</template>



<style lang="scss">

.container{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 25px;
    background-color: black;

    .site-name{
        text-transform: uppercase;
        font-weight: bold;
        color: red;
    }

    .search{
        display: flex;
        gap: 12px;

        > *{
            padding: 8px 12px;
            border-radius: 0.25em;
            border: none;
            cursor: pointer;
        }

        button{
            background-color: #242424;
        }
    }
}

</style>