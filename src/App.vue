<template lang="html">
  <div class="">
    <h1>World of Football</h1>
    <div class="">
      <footballers-list :footballers="footballers"></footballers-list>
    </div>


  </div>

</template>

<script>
import FootballersList from './components/footballers_list.vue'


export default {
  name: 'app',
  data() {
    return {
      footballers:[],
      footballers_list: null

    }
  },

mounted() {
  fetch('https://www.scorebat.com/video-api/v1/')
  .then(response => response.json())
  .then(footballers => this.footballers = footballers);

},
components: {
  'footballers-list' : FootballersList

}

}



</script>

<style lang="css" scoped>
</style>
