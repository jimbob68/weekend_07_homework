<template lang="html">
  <div >
    <h1>Football Teams</h1>
    <football-teams-list v-bind:footballTeams="footballTeams"></football-teams-list>
    <selected-team-details></selected-team-details>
     <!-- <select v-on:change="handleSelect" v-model="footballTeams">
      <option v-for:="(footballTeam) in footballTeams" :value="footballTeam">{{footballTeam.name}}</option>
     </select> -->
     <iframe src="https://www.scorebat.com/embed/" frameborder="0" width="600" height="760"   allow="autoplay; fullscreen" style="width:600px;height:760px;overflow:hidden;display:block;" class="_scorebatEmbeddedPlayer_"></iframe><div>(function(d, s, id) {
    var js, fjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s); js.id = id;
    js.src = 'https://www.scorebat.com/embed/embed.js?v=mto';
    fjs.parentNode.insertBefore(js, fjs);
  }(document, 'script', 'scorebat-jssdk'));</div>

  </div>
</template>

<script>
import eventBus from './main.js'
import FootballTeamsList from './components/FootballTeamsList.vue'
import SelectedTeamDetails from './components/SelectedTeamDetails.vue'

export default {

  data() {
    return {
      footballTeams:[],
      footballTeamsList: null,
      selectedTeamDetails: null,

    }
  },
  components: {
    'football-teams-list' : FootballTeamsList,
    'selected-team-details': SelectedTeamDetails


},

  mounted() {
    fetch('https://www.scorebat.com/video-api/v1/')
    .then(response => response.json())
    .then(footballTeams => this.footballTeams = footballTeams);
}

}



</script>

<style lang="css" scoped>
body {
  font-family: fantasy;
  line-height: 1.6;
  background: e8f7f0;
}
</style>
