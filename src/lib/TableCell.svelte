<script>
  export let row;
  export let col;
</script>

{#if col.key == 'id'}
	<b>{row[col.key]}</b>
{:else if (row[col.key] === "")}
  <div>No pet</div>
{:else if (col.key == 'pet')}
	<img src={ `../img/${row[col.key]}.png` } alt={row[col.key]}/>
{:else}
	<div>{row[col.key]}</div>
{/if}

<style>
  img {
    height: 19px;
  }
</style>