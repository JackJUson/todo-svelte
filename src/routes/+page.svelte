<svelte:head>
  <link rel="stylesheet" href="https://unpkg.com/@picocss/pico@1.5.7/css/pico.min.css">
</svelte:head>

<!-- ToDo List Input  -->
<div style="margin: 0 auto; padding: 20px; width: 700px;">
  <h2 style="text-align: center;">ToDo List</h2>
  <p>Enter your ToDo here</p>
  <div style="display: flex;">
    <input type="text">
    <button style="width: 200px; margin-left: 24px;">Add</button>
  </div>
</div>

<!-- ToDo List Item -->
<div style="display: flex; align-items: baseline; width: 700px; margin: 0 auto;">
  <input type="checkbox">
  <h4 style="flex-grow: 1">Grind everyday!!!!!</h4>
  <div style="display: flex;">
    <button>Edit</button>
    <button style="margin-left: 24px;">Delete</button>
  </div>
</div>