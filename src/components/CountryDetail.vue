<template>
    <div>
        <h1>Name: {{country.name}} </h1>
        <h2>Capital: {{country.capital}}</h2>
        <h2>Population: {{country.population}}</h2>
        <img :src=country.flag id="flag">
        <h2>Languages: </h2>
            <ul>
                <li v-for="(language, index) in country.languages" :key="index">{{language.name}}</li>
            </ul>
        
    </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']

}
</script>

<style lang='css' scoped>
    #flag {
        max-width: 300px;
    }


</style>