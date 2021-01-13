<template>
  <div id="app">


  <h1>Countries</h1>
  <div class="main-container">
    <countries-list :allCountries="allCountries"></countries-list>
    <!-- <countries-drop-down :allCountries="allCountries"></countries-drop-down> -->
    <country-detail v-if=selectedCountry :country="selectedCountry"></country-detail>
  </div>


  </div>
</template>

<script>
import { eventBus }  from './main.js'
import CountriesList from './components/CountriesList.vue'
import CountryDetail from './components/CountryDetail.vue'
import CountriesDropDown from './components/CountriesDropDown.vue'


export default {
  name: 'App',
  data(){
    return {
      allCountries: [],
      selectedCountry: null
      };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.allCountries = data);

    eventBus.$on('country-selected', (country) => {
        this.selectedCountry = country;
      })
    
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail,
    "countries-drop-down": CountriesDropDown
  }
}

</script>

<style lang="css">
  .main-container {
    display: flex;
    justify-content: space-between;
  }

</style>
