<script>
  import Button from "./Button.svelte";
  import Card from "./Card.svelte";

  let meme;

  function handleClick() {
    fetch("https://meme-api.herokuapp.com/gimme/1")
      .then((response) => response.json())
      .then((memes) => {
        meme = memes.memes[0];
      });
  }
</script>

<main>
  <h1>Meme generator</h1>
  <Card>
    {#if meme}
      <h2>{meme.title}</h2>
      <img src={meme.url} alt="meme" />
    {/if}
  </Card>
  <Button {handleClick} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  img {
    width: 100%;
    object-fit: contain;
  }

  h1 {
    color: #a9216b;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
