<template>
    <div class="p-2">
        <select name="" id="" v-model="statusFilter" @change=" $emit ('giuseppe', statusFilter)">
            <option value="">All</option>
            <option value="alien">Alien</option>
            <option value="Noble Knight">Noble Knight</option>
            <option value="divine dragon">Drakes</option>
            <option value="cyber dragon">cyber drago</option>
        </select>
        
    </div>
</template>

<script>
    export default {
        name: "selectorType",
        data(){
            return{
                statusFilter: '',
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>