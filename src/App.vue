<script setup>
import { ref } from "vue";
import countries from "../src/data/countries";

const search = ref("");

const getSearchCountry = () => {
  return countries.filter((country) => {
   return country.name.toLowerCase().startsWith(search.value.toLocaleLowerCase());
   
  });

};
</script>

<template>
  <section class="bg-gray-200 w-full h-screen mx-auto pt-10">
    <div class="container mx-auto">
      <h1 class="text-center font-bold text-3xl mb-10">All Country Search</h1>
      <p class="mb-5">{{ search }}</p>
      <input
        type="search"
        name=""
        id=""
        class="w-full mb-10"
        v-model="search"
      />
      <p class="mt-2" v-for="country in getSearchCountry()" :key="country.code">
        {{ country.name }}
      </p>
    </div>
  </section>
</template>

<style scoped></style>
