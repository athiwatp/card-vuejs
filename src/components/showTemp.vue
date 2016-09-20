<template lang="html">
  <div v-for="list in listOrder | orderBy '-vote' ">
   <img :src="list.url" width="200px" height="200px">
   <h3>{{list.name}} :  {{ list.price }} บาท</h3> <br>
   <button @click="addVote($index)">Vote up </button> <h3> {{ list.vote }} Vote </h3>
   <hr>
 </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  computed: {},
  ready () {},
  attached () {},
  methods: {},
  components: {},
  props: ['listOrder', 'addVote']
}
</script>

<style lang="css">
</style>
