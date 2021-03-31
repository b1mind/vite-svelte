<script>
  import { getStore, valueStore } from './hmr-stores'

  export let id

  const count = getStore(id, 0)
  const increment = () => {
    $count += 1
  }

  let counter = 0

  const clickCounter = () => counter++

  $: bigCounter = $count + counter
</script>

<button {id} on:click={increment}>
  Clicks: {$count}
</button>

<button on:click={clickCounter}> {counter} </button>

<p>Reactive with store: {$valueStore + bigCounter}</p>

<p>Reactive variable: {bigCounter}</p>

<style type="scss">
  button {
    font-family: inherit;
    font-size: inherit;
    padding: 1em 2em;
    color: #ff3e00;
    background-color: rgba(255, 62, 0, 0.1);
    border-radius: 2em;
    border: 2px solid rgba(255, 62, 0, 0);
    outline: none;
    width: 200px;
    font-variant-numeric: tabular-nums;

    &:focus {
      border: 2px solid #ff3e00;
    }

    &:active {
      background-color: black;
    }
  }
</style>
