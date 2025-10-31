<script setup>
// Import component
import DocumentCard from '@/components/documents/DocumentCard.vue'

// API URL
const baseUrl = "https://fdnd-agency.directus.app/items/";
const documentsEndpoint = "adconnect_documents";
const fields = "?fields=title,id,description,slug,hero_image,source_file,category.*,date";
const documentUrl = baseUrl + documentsEndpoint + fields;

// Data ophalen 
const { data: documents } = await useAsyncData('documents', async () => {
  const documentsResponse = await fetch(documentUrl);
  const documentsData = await documentsResponse.json();
  return documentsData.data;
});
</script>

<template>
  <main>
    <h1>Welkom op de homepage 🎉</h1>

    <div class="cards">
      <DocumentCard
        v-for="document in documents"
        :key="document.id"
        :document="document"
      />
    </div>
 </main>
</template>
