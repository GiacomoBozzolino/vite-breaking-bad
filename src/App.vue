<script>
import AppHeader  from './components/AppHeader.vue';
import AppMain  from './components/AppMain.vue';
// import AppTypeSearch from './components/AppTypeSearch.vue'

import axios from 'axios';
import {store} from './store.js';

export default {
  components:{
    AppHeader,
    AppMain,
    // AppTypeSearch,
  },
  data() {
    return {
      store,
    }
  },
  mounted() {
      this.getPokemonType()
    }, 
    methods:{
        getPokemonType(){
              
           store.newUrl  = store.apiUrl 
          if(store.selectedType !== ''){
             store.newUrl += `&eq[type1]=${store.selectedType}`
              console.log(store.selectedType)
          }
          
          axios.get(store.newUrl).then((response) => {
              store.pokedex = response.data.docs;
              console.log(response.data.docs)
            console.log('emit funzionante')
          })
        },
}

}
</script>

<template lang="">
<div>
<AppHeader @changeType="getPokemonType"/>

<AppMain/>
</div>
</template>


<style lang="scss">
@use '../styles/generals.scss' as *



</style>