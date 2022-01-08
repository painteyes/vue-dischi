<template>
    <section>
        <div class="container"> 
            <AlbumCard v-for="(element,index) in albums" :key="index" :albumObject="element" />
        </div>
    </section>
</template>


<script>

    import axios from "axios";
    import AlbumCard from "./AlbumCard.vue" ; 

    export default {

        name: 'AlbumsList',

        components: {
            AlbumCard,
        },

        data: function(){
            return{
                albums: [],
            }
        },

        created: function () {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) => {
                this.albums = response.data.response;
            })
        }
    }
</script>


<style scoped lang='scss'>

    section {
        color: white;
    }

    .container{
        width: 70%;
        margin: 50px auto;
        display: flex;
        flex-wrap: wrap;
    }

</style>