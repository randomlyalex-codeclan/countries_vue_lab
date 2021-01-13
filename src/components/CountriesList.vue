<template>
    <div>
        <countries-list-item v-for="(country, index) in allCountries" :country="country" :key="index"></countries-list-item>
    </div>
</template>

<script>

import CountriesListItem from './CountriesListItem.vue';
export default {
    name: 'countries-list',
    props: ['allCountries'],
    components: {
        "countries-list-item": CountriesListItem
    }
    
}
</script>

<style lang="css" scoped>

</style>