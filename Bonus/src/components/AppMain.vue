<script>
import AppCardList from '../components/AppCardList.vue';
import AppLoader from './AppLoader.vue';
// importo store dal file store.js
import {store} from '../store.js'; 

    export default {
        components:{
            AppCardList,
            AppLoader,
            store,

        },
        data() {
            return {
                store,
                
            }
        },

        
        
    }
</script>
<template lang="">
    <main>
        <div class="container" >
            <div class="card_container d-flex align-items-center justify-content-center">
               
                    <div v-if="store.loading === false" class="inner_container row">
                        <div v-for="(pokemon, index) in store.pokedex" :key="index"  class="col-sm-12 col-md-6 col-lg-3">
                            <AppCardList :myPokemon="pokemon"  />
    
                        </div>
                    </div>
                    <!-- Importo il loader -->
                    <AppLoader v-else/>
               

            </div>

          
        </div>

    </main>
</template>
<style lang="scss" scoped>
@use '../styles/partials/_variables' as *;

    main{
        background-color:$background_red;
        height: calc(100vh - 150px);  
    }

    .card_container{
        background-color: $background_white;
        height:75vh;
        width: 100%;
        border-radius: 30px;
        
        .inner_container{
            background-color: $background_grey;
            width: 95%;
            height: 90%;
            overflow-y: auto;
            
        }
        
    }
    
</style>