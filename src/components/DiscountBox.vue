<template>
  <div class="discount-code-box custom-form">
      <form>
        <div>
            <q-input outlined v-model="text" placeholder="Discount code">
            </q-input>
            <q-btn>Apply</q-btn>
        </div>
    </form>
  </div>
</template>
<script>
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'DiscountBox'
})
</script>
