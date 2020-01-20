<template lang="html">
<div v-if="footballTeam">
<h2>{{footballTeam.name}}</h2>
<!-- <h2>{{footballTeam.thumbnail}}</h2> -->
<!-- <div>
  <p>{{footballTeam.name}}</p>
  <p>{{footballTeam.video}}</p>

</div> -->
</div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'selected-team-details',
  data(){
    return {
      footballTeam: null
    }
  },
  mounted(){
    eventBus.$on('team-selected', (footballTeam) => {
      this.footballTeam = footballTeam
    })
  }
}
</script>

<style lang="css" scoped>
</style>
