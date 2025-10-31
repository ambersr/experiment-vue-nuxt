<template>
    <nav>
      <NuxtLink to="/" class="first">Menu item</NuxtLink>

      <div class="links">
        <NuxtLink to="/">Menu item</NuxtLink>
        <NuxtLink to="/">Menu item</NuxtLink>
      </div>
    </nav>
</template>

<style>
nav {
    display: flex;
    flex-direction: row;
    padding: 1.5em 0 1.5em 0;
    gap: 1em;
    background-color: var(--primary-blue);
    width: 100%;
    justify-content: space-between;
    border-radius: 0 0 1em 1em;
    position: sticky;
    top: 0;
    z-index: 99999;
    align-items: center;
}

.links {
    padding: 0 5% 0 0;
    display: flex;
    align-items: center;
    gap: 2em;
    justify-self: right;
}

.first {
    padding: 0 0 0 5%;
    color: var(--text-white);
}

nav a, nav p {
    color: var(--text-white);
    margin: 0;
}

</style>