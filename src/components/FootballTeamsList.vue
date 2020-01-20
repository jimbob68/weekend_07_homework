<template lang="html">
<div class="">

   <!-- <input type="text" v-model="search" placeholder="search for a team" v-on:keyup="searchForTeam"> -->
  <select v-on:change="handleSelect" v-model="selectedTeam">


  <option disabled value="">Select a Team</option>
  <option v-for="footballTeam, index) in footballTeams" :value="footballTeam" :key="index">{{ footballTeam.side1.name }}</option>

</select>




</div>

</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'football-teams-list',

  data(){
    return {
      "search": "",
      "selectedTeam": {},
    }
  },
  props: ['footballTeams'],
  methods:{
    searchForTeam(){
      let foundTeam = this.footballTeams.find((footballTeam) => {
        return footballTeam.name
  })
      this.selectedTeam = foundTeam

      eventBus.$emit('team-selected', this.selectedTeam)

  },
    handleSelect(){
      // this.search = ""
      eventBus.$emit('team-selected', this.selectedTeam)
    }
  }
}

</script>

<style lang="css" scoped>
</style>
