<template>
     <form @submit="addToCart()">
        <div class="row">
            <div class="col">
                <label for="category">Category</label>
                <select id="category" class="form-control">
                    <option 
                    v-for="(item, index) in items" 
                    :key="index"
                    :value="item.category" 
                    > {{ item.category }}
                    </option>
                </select>
            </div>
            <div class="col">
                <label for="product">Products</label>
                <select id="product" class="form-control">
                    <option 
                    v-for="(item, index) in items" 
                    :key="index"
                    :value="item.product" 
                    > {{ item.product }}
                    </option>
                </select>
            </div>
        </div>
        <div class="row">
            <div class="col">
                <label for="quantity">Quantity</label>
                <input type="range" class="custom-range" id="quantity" min="0" max="20" step="1" v-model="quantity">
                <input type="number" v-model="quantity" disabled/>
            </div>
            <div class="col">
                <button id="add" type="submit" class="btn btn-primary mt-4">Add</button>
            </div>
        </div>
    </form>
</template>

<script>
export default {
  name: 'addItem',
  props: {
    items: Array
  },
  data() {
      return {
          category: "",
          product: "",
          quantity: 0
      }
  },
  methods: {
      addToCart: function (item) {
          this.$emit('update-cart', item)
      }
  },
  created() {
        
  }
        
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
