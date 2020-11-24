<template>
    <tr>
        <td>{{ item.category }}</td>
        <td>{{ item.product }}</td>
        <td>{{ item.quantity }}</td>
        <td>{{ onlyOneTotalPrice }} $</td>
    </tr>  
</template>

<script>
export default {
  name: 'item',
  props: {
    item: Object
  },
  computed: {
      onlyOneTotalPrice: function () {
          return (this.item.price * this.item.quantity)*1;
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
