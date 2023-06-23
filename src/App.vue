    <script>
    import AppHeader  from './components/AppHeader.vue';
    import AppMain  from './components/AppMain.vue';
    import AppTypeSearch from './components/AppTypeSearch.vue'

    import axios from 'axios';
    import {store} from './store.js';

    export default {
      components:{
        AppHeader,
        AppMain,
        AppTypeSearch,
      },
      data() {
        return {
          store
        }
      },
      // mounted (){
      //   axios.get(store.apiUrl).then((response) => {
      //     store.pokedex = response.data.docs
      //     console.log(response.data.docs)
      //   })
      // }
    
    }
    </script>

<template lang="">
  <div>
    <AppHeader/>
   
    <AppMain/>
  </div>
</template>


<style lang="scss">
@use '../styles/generals.scss' as *


  
</style>