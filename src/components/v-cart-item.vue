<template>
  <div class="v-cart-item">
    <!--<img :src=" require(`../assets/images` + cart_item_data.image)" alt="">-->
    <div class="v-cart-item__info">
      <p>{{cart_item_data.name}}</p>
      <p>{{cart_item_data.price}}</p>
      <p>{{cart_item_data.article}}</p>
    </div>
    <div class="v-cart-item__quantity">
      {{cart_item_data.quantity}}
      <p>Кол-во</p>
    </div>
    <button @click="deleteFromCart">Удалить</button>
  </div>
</template>

<script>
export default {
name: "v-cart-item",
  props:{
    cart_item_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {}
  },
  computed:{},
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart')
    }
  },
  mounted() {
    this.$set(this.cart_item_data, 'quantity', 1)
  }
}
</script>

<style>
.v-cart-item{
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 0 8px 0 #e0e0e0;
}
</style>