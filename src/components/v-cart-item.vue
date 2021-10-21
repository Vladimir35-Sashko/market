<template>
    <div class="v-cart-item">
       <img class="v-catalog-img" :src="require('../assets/images/' + cart_item_data.image)" alt="img">
       <div class="v-cart-item__info"></div>
       <p>{{cart_item_data.name}}</p>
       <p>{{cart_item_data.price}}</p>
       <p>{{cart_item_data.article}}</p>
       <div class="v-cart-item__quantity">
         <p>Qty:</p>
         <span>
           <span class="quantity__btn" @click="decrementItem"> - </span>
         {{cart_item_data.quantity}}
           <span class="quantity__btn" @click="incrementItem"> + </span>
       </span>
       </div>
       <button class="btn" @click="deleteFromCart">Delete</button>

    </div>
</template>

<script>



export default {
    name:"v-cart-item",
    props: {
        cart_item_data:{
            type:Object,
            default(){
                return {}
            }
        }
    },
  data (){
      return {}
  },
    computed: {


    },
  methods:{
          decrementItem() {
        this.$emit('decrement')

    },
    incrementItem() {
      this.$emit('increment')

    },

    deleteFromCart() {
      this.$emit('deleteFromCart')

    }
  },
  mounted() {
      this.$set(this.cart_item_data,'quantity',1)
  }

}
</script>
<style scoped>
.v-cart-item{
    display: flex;
    flex-wrap: nowrap;
      justify-content: space-between;
    align-items: center;
  flex-basis: 25%;
  box-shadow: 0 0 8px 0;
  padding: 16px;
  margin-bottom: 16px;
  width: 70vw;
}
.quantity__btn {
  cursor: pointer;
}
    
</style>