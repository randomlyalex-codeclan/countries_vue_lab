<template>
    <p> {{selectedCountry.name}} </p>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['selected-country']

}
</script>

<style scoped>


</style>