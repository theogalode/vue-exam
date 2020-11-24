<template>
  <div class="container">
    <h1>My cart</h1>
    <h2>I prepare my cart for the week</h2>
    <br>
    <Items v-bind:items="items"/>
    <br>
    <hr>
    <br>
    <h2>Add some products in your cart</h2>
    <br>
    <AddItem v-bind:items="items"/>
  </div>
</template>

<script>
import Items    from '../components/Items'
import AddItem  from '../components/AddItem'
export default {
  name: 'cart',
  components: {
    Items,
    AddItem
  },
  data() {
    return {
      items:[
        {
          category: "Dairy products",
          product: "Milk",
          quantity: 4,
          price: 1.5
        },
        {
          category: "Protein",
          product: "Eggs",
          quantity: 4,
          price: 1.5
        },
      ]
    }
  },
  methods: {
    updateCart: function(e){
      this.items.push(e);
    },
    emptyCart: function () {
      this.items = [];
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
