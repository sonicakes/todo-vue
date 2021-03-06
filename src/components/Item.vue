<template>
  <div>
      <div :class="[item.checked ? 'checked' : '', 'form-group']">
      <label>{{item.text}}</label>
    <input :id="item.id" type="checkbox" @change="isChecked(item.id)">
  </div>
  </div>
</template>

<script>
export default {
  name: 'Item',
  props: {
      item: Object
  },
  methods: {
      isChecked(id) {
console.log(id, 'the state of checkbox is changed');
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.checked * {
    color: red; 
    text-decoration: line-through;
}
</style>
