<script>
  import Header from "./Header.svelte";
  import IndexView from "./IndexView.svelte";
  import MainNav from "./MainNav.svelte";
  import TextNoteView from "./TextNoteView.svelte";
  import ListView from "./ListView.svelte";

  import { store } from "./store.js";

  let noteType;

  store.subscribe(store => {
    noteType = store.noteType;
    console.log("store.noteType: ", store.noteType);
  });
  // initialise state
</script>

<style>

</style>

<Header />
<MainNav />
{#if noteType === 'textNote'}
  <TextNoteView />
{:else if noteType === 'list'}
  <ListView />
{:else if noteType === 'index'}
  <IndexView />
{/if}
