<template>
      <div>
        <h1> List of all units and tenants</h1>
        <UnitCard v-for="unit in units" :key="unit.id" :unit="unit"/>
      </div>
 
</template>

<script>
    import UnitCard from '@/components/UnitCard.vue'
    import axios from 'axios'
    export default {
        components: {
        UnitCard
      },
        data(){
            return {
                units: []
            }
        },
        created() {
            axios
            .get('http://localhost:3000/units')
            .then( response => {
                this.units = response.data
            })
            .catch(error => {
                console.log('There was an error: ' + error.response )
            })
        }
    }
</script>

<style  scoped>

</style>