<script>
  //con el export le indicamos que queremos que sea una prop
  export let initialCounter = 0;
  let contador = initialCounter;
  export let maxCouunter = 9;

  function handleClick() {
    contador++;
  }

  //declaración reactiva
  $: isEvenOrOdd = contador % 2 === 0 ? "Is Even" : "Is Odd";
  $: if (contador > maxCouunter) {
    console.log('limit contador')
    contador = 9;
  }

</script>

<main>
  <button on:click={handleClick}>Incrementar</button>
  <span>{contador}</span>
  <span>{isEvenOrOdd}</span>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
