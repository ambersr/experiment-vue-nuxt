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

<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 1.5em;
        padding: 3em 0;
        width: 90%;
        max-width: 1400px;
        margin: auto;

        @media (min-width: 768px) {
            padding: 4em 0;
        }
    }

    .cards {
        display: flex;
        flex-direction: column;
        list-style-type: none;
        gap: 1em;
        padding: 0;
        margin: auto;
        width: 100%;

        @media (min-width: 768px) {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(22em, 1fr));
        }
    }
</style>