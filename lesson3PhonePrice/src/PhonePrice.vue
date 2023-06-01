<template>
  <div id="classmates">
    <h1>Classmates' Cellphone Prices</h1>
    <ul>
      <li id="list" v-for="classmates in classmates" :key="classmates.name">
      STUDENT: {{ classmates.name }} : PRICE: {{ classmates.price }} $
      </li>
    </ul>
    <p>Total Price: {{ totalPrice }} $</p>
    <p>Average Price: {{ averagePrice }} $</p>
  </div>
</template>

<script>
import { computed, defineComponent, ref } from "vue";

export default defineComponent({
  name: "PhonePrice",
  components: {},
  setup() {
    const classmates = ref([
      { name: "Alice", price: 320 },
      { name: "Jonathan", price: 850 },
      { name: "Mike", price: 300 },
      { name: "John", price: 675 },
      { name: "Anna", price: 480 },
      { name: "Judy", price: 505 },
      { name: "Karen", price: 430 },
      { name: "Nick", price: 1905 },
      { name: "Mary", price: 530 },
      { name: "Suzy", price: 840 }
    ]);

    const totalPrice = computed(() => {
      return classmates.value.reduce((sum, classmates) => sum + classmates.price, 0) 
    });

    const averagePrice = computed(() => {
      return totalPrice.value / classmates.value.length;
    }); 

    return {
      classmates,
      totalPrice,
      averagePrice
    }
  }
})
</script>

<style>
#classmates {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
} 
</style>
