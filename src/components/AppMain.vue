<script>
    export default {
        
    }
</script>
<template lang="">
    <main>
        <div class="container" >
            <div class="card_container d-flex align-items-center justify-content-center">
                <div class="inner_container">

                </div>

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
        height:700px;
        width: 100%;
        border-radius: 30px;
        .inner_container{
            background-color: $background_grey;
            width: 95%;
            height: 90%;
            
        }
        
    }
    
</style>