<template lang="html">
  <div class="">
    <h1>World of Football</h1>
    <!-- <footballers-list-item/> -->
    <!-- </FootballersListItem> -->
  </div>

</template>

<script>



export default {
  name: 'app',
  data() {
    return {
      footballers:[]
    }
  },

mounted() {
  fetch('https://www.scorebat.com/video-api/v1/')
  .then(response => response.json())
  .then(footballers => this.footballers = footballers);
},
components: {
  // 'footballers-list-item' : FootballersListItem
},

}



</script>

<style lang="css" scoped>
</style>
