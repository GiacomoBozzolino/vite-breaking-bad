<script>
import {store} from '../store.js';
export default {
    data() {
            return {
                pokemonType:[
                'Bug',
                'Dark',
                'Dragon',
                'Electric',
                'Fairy',
                'Fighting',
                'Fire',
                'Flying',
                'Ghost',
                'Grass',
                'Ground',
                'Ice',
                'Normal',
                'Poison',
                'Psychic',
                'Rock',
                'Steel',
                'Water'
                ],
                store,
                
            }
        },
    
}
</script>

<template lang="">
    <div>
        <select name="type" id="type" :v-model="store.searchType" @click="$emit('search')" >
            <option value="" selected>All</option>
            <option  v-for="(type1, index) in pokemonType" :key="index" :value="type1"  >{{type1}}</option>
            
        </select>
</div>
</template>

<style lang="scss">
    
</style>