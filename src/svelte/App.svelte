<script>
  import Serial from './Serial.svelte';
  export let name;
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
  h1 {
    color: #3700ff;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
  h2 {
    margin-top: 2em;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <h2>Serial port</h2>
  <Serial />
</main>
