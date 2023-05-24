<template>
  <Students />
</template>

<script>
import { defineComponent } from 'vue';
import Students from "@/components/Students.vue"

export default defineComponent({
  name: "App",
  components: {
    Students
  },
  setup() {
    return {

    }
  }
})
</script>

<style>

</style>
