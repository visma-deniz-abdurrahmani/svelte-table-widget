<script>
  import Table from './lib/Table.svelte';
  import Widget from './lib/Widget.svelte';
</script>

<main>
  <Widget title="Pets"><Table /></Widget>
</main>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Open Sans', sans-serif;
    background-color: #f5f8fa;

    box-sizing: border-box;
  }

  :global(*) {
    box-sizing: inherit;
  }

  main {
    max-height: 100vh;
    max-width: 100vw;
    margin: 16px;

    display: grid;
    grid-template-rows: 1fr 1fr;
    grid-gap: 16px;
  }
</style>
