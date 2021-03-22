<template>
  <div>
      <div :class="{checked: item.checked}" class="form-group">
      <label>{{item.text}}</label>
    <input :id="item.id" type="checkbox" @change="isChecked()">
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
      isChecked() {
      this.item.checked = !this.item.checked;
        this.$emit('checked', this.item.checked);
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
