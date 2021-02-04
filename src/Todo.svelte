<script>
  import { fly, scale } from "svelte/transition";
  export let todo;
  export let remove;
</script>

<div
  class="notification"
  class:is-success={todo.completed}
  transition:fly={{ duration: 1000, x: 50 }}>
  <input type="checkbox" bind:checked={todo.completed} />
  {todo.title}
  <button class="delete" on:click={() => remove(todo)} />
</div>
