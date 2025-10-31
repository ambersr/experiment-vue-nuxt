<script setup>
// Haal de slug uit de route
const route = useRoute();
const slug = route.params.slug;

// API data ophalen met behoud van variabelen
const { data: document } = await useAsyncData(`document-${slug}`, async () => {
  const baseUrl = "https://fdnd-agency.directus.app/items/";
  const documentEndpoint = "adconnect_documents";
  const fields = "fields=title,id,description,slug,hero_image,source_file.*,date";
  const filter = `?filter[slug][_eq]=${slug}`;

  const documentResponse = await fetch(`${baseUrl}${documentEndpoint}${filter}&${fields}`);
  const documentData = await documentResponse.json();

  return documentData.data[0]; // een enkel document
});
</script>

<template>
  <main>
    <h1>{{ document.title }}</h1>
    <p>{{ document.description }}</p>
  </main>
</template>

<style>

</style>