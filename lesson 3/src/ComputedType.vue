<template>
  <div class="price-block">
    <p>Original Price: {{ originalPrice }}</p>
    <input type="number" v-model="discount">
    <p>Discount: {{ discount }}</p>
    <p>Final Price: {{ finalPrice }}</p>
  </div>
</template>

<script>
import { defineComponent, ref, computed } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {

    const originalPrice = ref(100)
    const discount = ref(null)

    const finalPrice = computed(() => {
      return originalPrice.value - discount.value;
    })

    return {
      originalPrice,
      discount,
      finalPrice
    }
  }
})
</script>

<style>

</style>
