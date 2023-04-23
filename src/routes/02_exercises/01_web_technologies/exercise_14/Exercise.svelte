<script>
  let current = "";
</script>

<style>
  .red_btn {
    background-color: red;
  }
</style>

<!-- We will cover buttons later on! -->
<button class="btn btn-secondary" class:red_btn={current == "messi"} on:click={() => (current = "messi")}>
  Messi 
</button>

<button class="btn btn-secondary" class:red_btn={current == "ronaldo"}  on:click={() => (current = "ronaldo")}>
  Ronaldo
</button>

<button class="btn btn-secondary" class:red_btn={current == "neymar"} on:click={() => (current = "neymar")}>
  Neymar
</button>


