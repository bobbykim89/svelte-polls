<script>
  import PollDetails from './PollDetails.svelte'
  import PollStore from '@/stores/Pollstore'
  // import { onDestroy, onMount } from 'svelte'

  // const unsub = PollStore.subscribe((data) => {
  //   polls = data
  // })

  // Lifecycle hooks
  // onMount(() => {
  //   // maybe get data from a db
  //   console.log('component mounted')
  // })

  // onDestroy(() => {
  //   // undsub from store
  //   console.log('component destroyed')
  //   unsub()
  // })
</script>

<div class="poll-list">
  {#each $PollStore as poll (poll.id)}
    <div>
      <PollDetails {poll} on:vote />
    </div>
  {/each}
</div>

<style>
  .poll-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
</style>
