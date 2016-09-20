<template>
  <div class="hello">
    Url : <input type="text" v-model="list.url"> <br>
    Name : <input type="text" v-model="list.name"> <br>
    Price : <input type="number" v-model="list.price"> <br>
    <button type="button" @click="addListOrder(list)">Submit</button>
    <hr>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list: {}
    }
  },
  props: ['addListOrder']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
