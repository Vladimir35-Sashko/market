<template>
    <div class="v-catalog-item">
        <img class="v-catalog-img" :src="require('../assets/images/' + product_data.image)" alt="img">
        <p class="v-catalog-item_name">{{product_data.name}}</p>
        <p class="v-catalog-item_price">Price:{{product_data.price}}</p>
        <button class="v-catalog-item_add_to_cart_btn btn"
        @click="addToCart"
        >Add to cart</button>
    </div>
</template>

<script>
export default {
    name:"v-catalog-item",
    props: {
        product_data: {
            type:Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return {}
    },
    computed: {
    },
    methods: {
        addToCart() {
            this.$emit('addToCart',this.product_data);
        }
    }
}
</script>


<style>
.v-catalog-item {
    flex-basis: 25%;
    box-shadow: 0 0 8px 0;
    padding: 16px;
    margin-bottom: 16px;
}
.v-catalog-img {
  width: 200px;
  height: 200px;
}
.btn{
  padding: 8px 16px;
  background: #206ab1;
  color: #ffffff;
  border: 0;
  }
    
</style>