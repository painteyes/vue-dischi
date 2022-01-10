<template>
    <div class="filter">
        <select @change="filterByGenre" v-model='selectedValue' name="" id="">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Pop">Pop</option>
        </select>
    </div>
</template>


<script>
export default {
    name: "FilterSelected",
    data: function(){
        return {
            selectedValue: "",
        }
    },
    methods: {
        filterByGenre: function () {
            this.$emit('selectionChanged', this.selectedValue);
        }
    }
}
</script>


<style lang="scss" scoped>
    .filter{
        background-color: white;
        padding: 10px;
    }
</style> 