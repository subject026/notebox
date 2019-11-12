<script>
  import { store } from "./store.js";

  let noteType;

  store.subscribe(store => {
    noteType = store.noteType;
  });

  const handleNoteTypeChange = event => {
    store.update(store => {
      return {
        ...store,
        noteType: event.target.value
      };
    });
  };
</script>

<nav>
  <select on:change={handleNoteTypeChange}>
    <option value="textNote">text note</option>
    <option value="list">list</option>
  </select>
</nav>
