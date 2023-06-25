<script>
import {store} from '../store.js';

    export default {
        // recupero la props
    props:{
        myPokemon:Object,
    },
    data() {
        return {
            store,
        }
    },
    computed:{
        bgColor(){
            return store.pokemon_color[this.myPokemon.type1]
        }
    }
    }
  


</script>

<template lang="">
    <div class="poke-card text-center m-3" :style="`background-color: ${bgColor}`">
        <img :src="myPokemon.imageUrl" alt="">
        <div >{{myPokemon.number}}</div>
        <div class="fw-bold">{{myPokemon.name}}</div>
        <div class="pb-3 fst-italic">{{myPokemon.type1}}</div>

    </div>
</template>

<style lang="scss" scoped>
.poke-card{
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgba(191, 181, 237, 0.759);
    border-radius: 20px;
    img{
        padding: 10px;
        width: 190px;
        height: 190px;
        border-radius: 50%;
    }
}
    
</style>