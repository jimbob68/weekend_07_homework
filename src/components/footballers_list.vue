<template lang="html">
  <div class="">
<ul>
  <li v-for="(footballer, index) in footballers" :value="footballer" :key="index">{{ footballer.side1.name }}</li>
</ul>

  </div>
</template>

<script>

export default {
  name: 'footballers-list',
  props: ['footballers'],
  methods:{

  }


}
</script>

<style lang="css" scoped>
</style>
