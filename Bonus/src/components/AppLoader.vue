<script>
    export default {
        
        
    }
</script>

<template lang="">
    <div class="load-page">
          <img class="loader" src="public/Poké_Ball_icon.png" alt=""> 
    </div>
</template>

<style lang="scss" scoped>


.load-page{
  height: 100%;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.loader {
  width: 200px;
  height: 200px;
  -webkit-animation: spin 2s linear infinite; /* Safari */
  animation: spin 2s linear infinite;
}

/* Safari */
@-webkit-keyframes spin {
  0% { -webkit-transform: rotate(0deg); }
  100% { -webkit-transform: rotate(360deg); }
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>