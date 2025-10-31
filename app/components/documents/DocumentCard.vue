<script setup>
defineProps({
  document: {
    type: Object,
    required: true
  }
});
</script>

<template>
  <article>
    <h2 class="truncate two">{{ document.title }}</h2>
    <p class="truncate two">{{ document.description }}</p>

    <NuxtLink class="button-outline-blue" :to="`/${document.slug}`">
      Meer informatie
    </NuxtLink>
  </article>
</template>
