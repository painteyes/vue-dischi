<template>
    <div class="single-album">

        <div class="single-album-poster">
            <img :src="albumObject.poster" alt="">
        </div>

        <div class="single-album-title"> 
            {{albumObject.title}}
        </div>

        <div class="single-album-author">
            {{albumObject.author}}
        </div>

        <div class="single-album-year"> 
            {{albumObject.year}}
        </div>
    </div>
</template>


<script>
    export default {
        name:'AlbumCard',
        props: {
            albumObject: Object,
        }
    }
</script>


<style scoped lang='scss'>

    @import "../style/variables.scss";

    .single-album{
        background-color: #2e3a46;
        padding: 10px;
        margin: 15px ;
        width: calc((100% / 5) - 30px);
        text-align: center;

        &-title{
            color: white;
            text-transform: uppercase;
            font-size: 16px;
            font-weight: bold;
            padding: 15px 0;
        }

        &-author{
            color: $text-color;
            font-size: 15px;
        }

        &-year{
            color: $text-color;
            font-size: 14px;
        }
    }

</style>