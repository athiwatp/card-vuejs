<template>
  <div id="app">
    <input-temp :add-list-order="addListOrder"></input-temp>
    <show-temp :list-order="listOrder" :add-vote="addVote"></show-temp>
  </div>
</template>

<script>
import inputTemp from './components/inputTemp'
import showTemp from './components/showTemp'

export default {
  data () {
    return {
      listOrder: [
        {
          url: 'https://3.bp.blogspot.com/-u9QmBob0h3o/VtkSVOTRUvI/AAAAAAAAAmM/AouDAlu0bR8/s400/%25E0%25B8%259B%25E0%25B8%25B5%25E0%25B8%2581%25E0%25B9%2584%25E0%25B8%2581%25E0%25B9%2588%25E0%25B8%2597%25E0%25B8%25AD%25E0%25B8%2594%25E0%25B8%2599%25E0%25B9%2589%25E0%25B8%25B3%25E0%25B8%259B%25E0%25B8%25A5%25E0%25B8%25B2_Fried%2Bchicken%2Bwing%2Bsauce.jpg',
          name: 'ไก่ทอด',
          price: 0,
          vote: 0,
          id: Date.now()
        }
      ]
    }
  },
  components: {
    inputTemp: inputTemp,
    showTemp: showTemp
  },
  methods: {
    addListOrder: function (list) {
      var data = {
        url: list.url,
        name: list.name,
        price: list.price,
        vote: 0,
        id: Date.now()
      }
      this.listOrder.push(data)
    },
    addVote: function (id) {
      var index = this.listOrder.map(item => item.id).indexOf(id)
      console.log('vote ' + index)
      this.listOrder[index].vote += 1
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
