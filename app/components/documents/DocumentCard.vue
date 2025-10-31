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

<style>
    article {
        display: flex;
        flex-direction: column;
        gap: 1.5em;
        border: 1px solid #CCCCCC;
        border-radius: 1em;
        padding: 2em;
        transition: .2s ease-in-out;

        &:hover {
            border: 1px solid #00408D;
            box-shadow: 0 3px 10px rgba(141, 141, 141, 0.2);
            translate: 0 -1%;
            transition: .2s ease-in-out;
        }
    }

    .card-info {
        gap: 1em;
        display: flex;
        flex-direction: row;

        span {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: .5em;
        }
    }

    article h2, article p {
        margin: 0;
        width: 100%;
    }

    h2{
        font-size: 25px;
        height: 2.5em;
    }

    /* Truncate words */
    .truncate {
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box; 
        -webkit-box-orient: vertical;
        }

    /* Truncate one sentence */
    .truncate.single {
        white-space: nowrap;
        -webkit-line-clamp: 1;
    }

    /* Truncate two sentences */
    .truncate.two {
        -webkit-line-clamp: 2;
    }
  
</style>
