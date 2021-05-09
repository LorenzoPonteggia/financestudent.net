<script>
  export let status;
  export let error;

  const dev = process.env.NODE_ENV === "development";
</script>

<h1>Error {status}</h1>
<h2>There was an error!</h2>
{#if dev}
  <h2 style="font-size:25px">{error.stack}</h2>
{/if}
