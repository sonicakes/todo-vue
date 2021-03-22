<template>
  <div id="app">
    <Header/>
    <Items :items="items" @item-checked="childChecked"/>
    <Buttons />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Items from './components/Items.vue'
import Buttons from './components/Buttons.vue'

export default {
  name: 'App',
  components: {
    Header,
    Items,
    Buttons
  },
  methods: {
        childChecked(id) {
      this.items = this.items.map((item) =>
        item.id === id ? { ...item, checked: !item.checked } : item
      );
    },
  },
   created() {
    this.items = [
      {
        id: 1,
        text: "Vet Appointment",
        checked: false
      },
      {
        id: 2,
        text: "Hair Appointment",
        checked: true

      },
      {
        id: 3,
        text: "Study Appointment",
        checked: false

      },
    ];
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
