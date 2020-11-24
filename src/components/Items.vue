<template>
  <div class="container">
    <table class="table table-hover">
        <thead>
            <tr>
                <th scope="col">Categories</th>
                <th scope="col">Product</th>
                <th scope="col">Quantity</th>
                <th scope="col">Price</th>
            </tr>
        </thead>
        <tbody>
            <Item 
            v-for="(item, index) in items"
            :key="index"
            :item="item"
            />
        </tbody>
        <tfoot>
            <tr>
                <th scope="col">Total</th>
                <th colspan="2"></th>
                <th scope="col" > {{ totalCartPrice }} $</th>
            </tr>
        </tfoot>
    </table>
  </div>
</template>

<script>
import Item from '../components/Item'
export default {
  name: 'items',
  components: {
      Item
  },
  props: {
    items: Array
  },
  computed: {
      totalCartPrice: function () {
          let price = 0;
          this.items.forEach(item => {
              price += (item.price * item.quantity)*1
          });
          return price;
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
