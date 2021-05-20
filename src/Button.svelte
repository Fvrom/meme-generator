<script>
  export let handleClick;
</script>

<button on:click={handleClick}> Get random meme </button>

<style>
  button {
    height: 5rem;
    width: 16rem;
    margin-top: 1rem;
    font-size: 1.6rem;
    border: none;
    border-radius: 0.2rem;
    background-color: #2e9699;
    align-self: center;
  }
</style>
