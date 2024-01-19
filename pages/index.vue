<script setup>
const { data: hello } = await useFetch("/api/hello");
const { data } = await useFetch("/api/disney");
const characters = data;
const clientSideExample = "Disney Characters";
</script>

<template>
  <main>
    <header>
      <h1>Assignment 2 - Data Fetching</h1>
    </header>

    <section>
      <h2>1. Nuxt Setup & Git Management
      </h2>
        <p>Correct scaffolding
        git commits at least 2 (partial marks)<p>
          Commits >= 5 (full marks)
        </p></p>
      <h2>2. Server Route Code
      </h2>
        <p>
          Async fetch function
        </p>
        <p>
          Nuxt server boiler plate code setup
        </p>
        <p>
          Naming conventions for files
        </p>
        <p>
          Data returned
        </p>
      <h2>3.Client Side Code
      </h2>
        <p>
          UseFetch composable
        </p>
        <p>
          Rendered on the page
        </p>
        <p>
          Pre tags for partial marks
        </p>
        <p>
          V-for loop with data binding for full marks
        </p>
      <h2>4. Deployment
      </h2>
      <p>
        full deployment === full marks
      </p>
      <p>
        broken deployment === 1/2 marks
      </p>
      <p>
        no deployment === no marks
      </p>
      <h1>{{ clientSideExample }}
      </h1>
    </section>
    <pre>{{ characters }}</pre>
    <section>
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