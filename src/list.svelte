<script>

  import { currentAnimal } from './store.js'

  export let animals = []

  const selectAnimal = (animal) => () => { $currentAnimal = animal }

</script>
<style>
  .list {
    margin: 0;
    padding: 0;
  }
  .item {
    text-transform: capitalize;
    padding-bottom: 10px;

    list-style: none;
  }
</style>
<h1>Zodiac List:</h1>
<ul class="list">
  {#each animals as animal}
    <li class="item" on:click={selectAnimal(animal)}>{animal.name}</li>
  {/each}
</ul>
