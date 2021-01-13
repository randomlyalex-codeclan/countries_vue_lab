<template>
    <div>
        <h1> {{country.name}} </h1>
        <h2>{{country.capital}}</h2>
        <img :src=country.flag id="flag">
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