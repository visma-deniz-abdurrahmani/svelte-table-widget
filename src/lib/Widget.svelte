<script>
  export let title;
</script>

<div>
  <h1>{title}</h1>
  <slot />
</div>

<style>
  div {
    background-color: #fff;
    padding: 16px;
    border: 1px solid #e1e8ed;
    border-radius: 4px;
  }

  h1 {
    font-size: 16px;
    font-weight: 600;
    color: #333333;

    margin: 0;
    padding-bottom: 16px;

    border-bottom: 1px solid #e1e8ed;
  }
</style>