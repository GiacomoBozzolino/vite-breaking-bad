<script>
    // import AppTypeSearch from '../components/AppTypeSearch.vue'
    import {store} from '../store.js';
    import axios from 'axios';
    export default {

        data() {
            return {
                store,
                pokemon_types: [
                    "Bug",
                    "Dark",
                    "Dragon",
                    "Electric",
                    "Fairy",
                    "Fighting",
                    "Fire",
                    "Flying",
                    "Ghost",
                    "Grass",
                    "Ground",
                    "Ice",
                    "Normal",
                    "Poison",
                    "Psychic",
                    "Rock",
                    "Steel",
                    "Water"
                ],
            }
        },
        components:{
            // AppTypeSearch,
        },
        methods:{
            resetSearch(){
                store.searchText = '';
                store.selectedType = '';
                this.$emit('changeType')

            }
        }
        
        
    }


</script>
<template lang="">
    <header>
        <div class="container">
            <div class="d-flex pt-2 justify-content-between">
                <div class="d-flex">
                    <div class=pt-3>
                        <button id="button-big"></button>
                    </div>
                    <div>
                        <button id="button-1"></button>
                        <button id="button-2"></button>
                        <button id="button-3"></button>
                    </div>
                </div>
                <div class="d-flex align-items-center">
                    <div class="p-2">
                        <input class="form-control mr-sm-2" type="text" id="search" v-model="store.searchText" placeholder=" Search your Pokemon..." >
                    </div>
                    <div class="p-2">
                        <select class="form-select select-bar "  v-model="store.selectedType"   >
                            <option value="" selected>All</option>
                            <option v-for="(type, index) in pokemon_types" :key="index" :value="type" >{{type}}</option>
                        </select>
                    </div>
                    <div class="p-2">
                        <button class="btn btn-primary" @click="$emit('changeType')">Search</button>
                    </div>
                    <div class="p-2">
                        <button class="btn btn-warning" @click="resetSearch">Reset </button>
                    </div>
                </div>
            </div>   
        </div>
    </header>
</template>


<style lang="scss" scoped>
@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixis?' as*;

    header{
        background-color:$background_red ;
        height: 150px;
    }



    #button-big{
        @include roundButton (80px, 80px, rgb(0, 21, 255))
    }
    #button-1{
        @include roundButton (50px, 50px, red)
    }
    #button-2{
        @include roundButton (50px, 50px, rgb(206, 206, 0))
    }
    #button-3{
        @include roundButton (50px, 50px, green)
    }




</style>