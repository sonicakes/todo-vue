<template>
  <div>
    <h2>This is items list</h2>
  <div class="items-list" div v-for="item in items" :key="item.id">
<Item :item="item" @checked="onClickChild"/>
  </div>

  </div>
</template>

<script>
import Item from './Item'

export default {
  name: 'Items',
  components: {
Item
  },
  props: {
      items: Array
  },
  methods: {
      onClickChild () {
        this.$emit('item-checked', this.item.id);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
