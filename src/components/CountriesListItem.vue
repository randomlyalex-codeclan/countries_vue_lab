<template>
    <li v-on:click="handleClick">{{country.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'countries-list-item',
    props: ['country'],
    methods: {
        handleClick: function() {
            eventBus.$emit('country-selected', this.country);
        }
    }
}
</script>

<style >

</style>