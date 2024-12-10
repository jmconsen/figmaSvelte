<script>
  export let text = 'Botón';
  export let onClick = () => {};
</script>

<button on:click={onClick}>{text}</button>

<style>
  button {
    padding: 0.5rem 1rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
</style>