<template>
  <div class="order-list">
      <div class="details-box">
          <div class="thumb-img">
            <img :src= image alt="">
        </div>
        <div class="p-summary-details">
            <div class="title">{{ title }}</div>
            <div class="qty">x{{ qty }}</div>
        </div>
      </div>
      <div class="price-box">
          <div class="price">{{ price }}</div>
      </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'OrderSummary',
  props: {
    title: {
      type: String,
      required: true
    },
    qty: {
      type: String,
      default: ''
    },

    image: {
      type: String,
      default: '#'
    },

    price: {
      type: String,
      default: ''
    }
  }
})
</script>
