<script setup>
import { reactive, ref } from 'vue';


const persons = reactive([
  {
    name: "Momin Khan",
    age: 25,
    position: "Developer"
  },
  {
    name: "Sazan Sarker",
    age: 24,
    position: "Photographer"
  },
  {
    name: "Imran H0ssen",
    age: 26,
    position: "EEE Eng."
  },
  {
    name: "Kawser Ahmes",
    age: 24,
    position: "Textile Eng"
  }
])

const activeIndex = ref(0)

</script>

<template>
 <section class="bg-gray-200 w-full h-screen">
  <div class="container mx-auto">
    <h1 class="text-center pt-20 pb-10 font-bold text-3xl">Vue Form</h1>
    <p class="mb-5">{{ persons }}</p>
    <div class="grid grid-cols-2">
      <div>
        <p class="mb-5">{{ activeIndex }}</p>
        <select name="person" id="person" class="w-3/4 border-none" v-model="activeIndex">
          <option :value="index"  v-for="(person, index) in persons" :key="index">{{ person.name }} </option>
        </select>
      </div>
      <div class="flex flex-col gap-4">
        <input class="w-3/4" type="text" name="" id="" v-for="(value, key, index) in persons[activeIndex]" :key="key" v-model="persons[activeIndex][key]">
      </div>
    </div>
    
  </div>
 </section>
</template>

<style scoped>

</style>
