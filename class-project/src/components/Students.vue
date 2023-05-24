<template>
  <div class="class">
    <ul v-for="student in arrayStudents" :key="student.name">
        <li>
            {{ student.name }} - {{ student.age }}. Height: {{ student.height }}. Hobby: {{ student.hobby }}
        </li>
    </ul>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
    // eslint-disable-next-line vue/multi-word-component-names
    name: "Students",
    setup() {
        const arrayStudents = [
            { name: "Oleg Katsurov", age: 20, height: "183", hobby: "sports" },
            { name: "Anna Nekrasova", age: 22, height: "171", hobby: "swimming" },
            { name: "Svitlana Semkina", age: 21, height: "165", hobby: "bicycling" },
            { name: "Pavlo Durov", age: 20, height: "178", hobby: "cooking" },
            { name: "Olga Popova", age: 22, height: "159", hobby: "fishing" },
            { name: "Dmutro Sinelnikov", age: 19, height: "190", hobby: "driving" },
            { name: "Mykyta Koliadin", age: 23, height: "184", hobby: "nothing" },
        ]
        return {
            arrayStudents
        }
    }
})
</script>

<style scoped>

</style>
