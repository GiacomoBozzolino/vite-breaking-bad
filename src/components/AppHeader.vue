<script>
    import AppTypeSearch from '../components/AppTypeSearch.vue'
    import {store} from '../store.js';
    import axios from 'axios';
    export default {

        data() {
            return {
                store,
            }
        },
        components:{
            AppTypeSearch,
            

        },
        mounted (){

            this.getType()
        
        },

        methods: {
            getType(){
                console.log(store.searchType)
                axios.get(store.apiUrl).then((response) => {
                store.pokedex = response.data.docs
                console.log(response.data.docs)
                console.log('emit funzionante')
        })
            },
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
                <div>
                    <AppTypeSearch @search="getType" />
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