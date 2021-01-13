<template>
  <div id="app">
  <h1>Countries</h1>
    <countries-list :allCountries="allCountries"></countries-list>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'


export default {
  name: 'App',
  data(){
    return {
      allCountries: [],
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.allCountries = data)

  },
  components: {
    "countries-list": CountriesList
  }
}
</script>

<style>

</style>
