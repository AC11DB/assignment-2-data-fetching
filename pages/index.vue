<script setup>
const { data: hello } = await useFetch("/api/hello");
const { data } = await useFetch("/api/disney");
const characters = data;
const clientSideExample = "This an example of fetched data";
</script>

<template>
  <main>
    <header>
      <h1>Assignment 2 - Data Fetching</h1>
    </header>

    <section>
      <h2>Student: Angelica Cadiz</h2>
      <p>{{ hello.hello }}</p>
      {{ clientSideExample }}
      <h2>Disney Character Fetch</h2>
      <ul>
        <li v-for="character in characters.data" :key="character.id">
          <h3>{{ character.name }}</h3>
          <img :src="character.imageUrl" />
        </li>
      </ul>
    </section>
  </main>
</template>
