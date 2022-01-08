<template>
  <div id="app">
    
    <Header/>

    <main>
      <AlbumsList/>
    </main>
 
  </div>
</template>


<script>

  import Header from "./components/Header.vue" ;
  import AlbumsList from "./components/AlbumsList.vue" ;

  export default {
    name: "App",
    components: {
      Header,
      AlbumsList,
    },
  };
  
</script>


<style lang="scss">

@import './style/general.scss';
@import "./style/variables.scss";

</style>
