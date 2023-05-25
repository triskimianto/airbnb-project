<template>
  <div class="container">
    <NuxtLayout :name="comingsoon"></NuxtLayout>
  </div>
</template>

<style>
  .container{
    max-width: 100%;
  }
</style>

<script setup>
  const comingsoon = "comingsoon";
</script>