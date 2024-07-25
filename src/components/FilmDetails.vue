<template>
  <div class="border rounded-md p-4">
    <h2 class="text-xl font-bold mb-2">{{ film.title }}</h2>
    <p><strong>Director:</strong> {{ film.director }}</p>
    <p><strong>Productor:</strong> {{ film.producer }}</p>
    <p><strong>Fecha de lanzamiento:</strong> {{ film.release_date }}</p>
    <p><strong>Introducción:</strong> {{ film.opening_crawl }}</p>
  </div>
</template>

<script>
export default {
  props: ['film']
}
</script>

<style>
  .cursor-pointer {
    cursor: pointer;
  }
</style>