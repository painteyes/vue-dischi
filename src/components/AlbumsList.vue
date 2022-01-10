<template>
    <section>

        <FilterSelected @selectionChanged='setSelectionValue'/>

        <div class="container"> 
            <AlbumCard v-for="(element,index) in filteredAlbums()" :key="index" :albumObject="element" />
        </div>
    </section>
</template>


<script>

    import axios from "axios";
    import AlbumCard from "./AlbumCard.vue" ; 
    import FilterSelected from "./FilterSelected.vue" ; 



    export default {

        name: 'AlbumsList',

        components: {
            AlbumCard,
            FilterSelected,
        },

        data: function(){
            return{
                albums: [],
                selectionValue: "",
            }
        },

        methods: {

            setSelectionValue: function(selectedValue) {
                this.selectionValue = selectedValue;
            },

            filteredAlbums: function() {

                if (this.selectionValue === "") {
                    return this.albums;
                }

                const filteredArray = this.albums.filter((album)=>{
                    return album.genre === this.selectionValue;
                })
    
                return filteredArray;
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