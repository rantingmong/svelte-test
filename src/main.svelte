<script>

  import List    from './list'
  import Content from './content'

  import { currentAnimal } from './store.js'

  import animals from './animals.json'

  $: showContent = $currentAnimal != null

</script>
<style>
  :global(body) {
    margin: 15px;
    font-family: sans-serif;

    position: absolute;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
  }

  .screen {
    display: grid;
    grid-template-columns: 300px auto;
    grid-template-rows: 1fr;
    height: 100%;

    border: 1px gray solid;
    border-radius: 5px;
  }

  .left {
    border-right: 1px gray solid;
    padding: 15px;
  }

</style>

<div class="screen">
  <div class="left">
    <List animals={animals}/>
  </div>
  <div class="content">
    {#if showContent}
      <Content animal={$currentAnimal}/>
    {:else}
      <p>Select an animal to start~</p>
    {/if}
  </div>
</div>
