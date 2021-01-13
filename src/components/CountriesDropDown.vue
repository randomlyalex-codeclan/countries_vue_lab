<template>
    <div>
        <select>
            <option v-for="country in allCountries" :value="country"> {{ country.name }} </option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'countries-drop-down',
    props: ['allCountries']

}
</script>

<style lang="css" scoped>

</style>