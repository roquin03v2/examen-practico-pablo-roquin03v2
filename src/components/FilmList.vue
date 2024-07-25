<template>
  <div class="border rounded-md p-4">
    <h2 class="text-xl font-bold mb-2">Películas</h2>
    <ul class="list-disc pl-4">
      <li v-for="(film, index) in films" :key="index" class="cursor-pointer" @click="$emit('film-selected', film)">
        {{ film.title }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['films']
}
</script>

<style>
  .cursor-pointer {
    cursor: pointer;
  }
</style>
  