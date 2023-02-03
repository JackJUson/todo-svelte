<script>
	let toDoList = [1, 2, { content: 'Grind or go home!', editing: true, checked: true }]; // Aarry of ToDos

  function setEditing(i, isEditing) {
    toDoList[i].editing = isEditing; // true or false
  }
</script>

<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/@picocss/pico@1.5.7/css/pico.min.css" />
</svelte:head>

<!-- ToDo List Input  -->
<div style="margin: 0 auto; padding: 20px; width: 700px;">
	<h2 style="text-align: center;">ToDo List</h2>
	<p>Enter your ToDo here</p>
	<div style="display: flex;">
		<input type="text" />
		<button style="width: 200px; margin-left: 24px;">Add</button>
	</div>
</div>

<!-- ToDo List Item -->
{#each toDoList as toDo, i}
	<div style="display: flex; align-items: baseline; width: 700px; margin: 0 auto;">
		{#if toDo.editing}
			<input type="text" bind:value={toDo.content} />
		{:else}
			<input type="checkbox" bind:checked={toDo.checked} />
			<h4 style="flex-grow: 1">{toDo.content}</h4>
		{/if}
		<div style="display: flex;">
      {#if toDo.editing}
			<button on:click={() => setEditing(i, false)} style="margin-left: 24px;">Save</button>
      {:else}
			<button on:click={() => setEditing(i, true)} style="margin-left: 24px;">Edit</button>
      {/if}
			<button style="margin-left: 24px;">Delete</button>
		</div>
	</div>
{/each}
