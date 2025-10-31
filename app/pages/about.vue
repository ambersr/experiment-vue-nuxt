<script setup>
import { useHead } from '#app'

useHead({
  title: 'About | Experiment Vue/Nuxt',
  htmlAttrs: {
    lang: 'nl' // hier kun je 'en' of een andere taal zetten
  },
});
</script>

<template>
  <div class="container">
    <h1>About</h1>
    <p>Dit is de About pagina van je site.</p>
  </div>
</template>