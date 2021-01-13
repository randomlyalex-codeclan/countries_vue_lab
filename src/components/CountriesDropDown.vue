<template>
    <div>
        <select v-model="dropDownSelect" v-on:change="handleChange">
            <option v-for="(country, index) in allCountries" :key="index" :value="country"> {{ country.name }} </option>
        </select>
    </div>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'countries-drop-down',
    data(){
    return {
      dropDownSelect: null
      };
    },
    props: ['allCountries'],
    methods:{
        handleChange: function() {
            // console.log(event.target.value);
            eventBus.$emit('country-selected', this.dropDownSelect);
        }

    }

}
</script>

<style lang="css" scoped>

</style>