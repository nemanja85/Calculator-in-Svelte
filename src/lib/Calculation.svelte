<script>
  let total = 0;
  let state = null;
  let console = '';

  function setOperation(operation){

  }
</script>

<div class="calculator">
  <input type="text" bind:value={console} />
  <div class="buttons">
    <div class="operations">
        <button on:click={() =>{setOperation('add');}}>
        +
      </button>
      <button on:click={() =>{setOperation('substract');}}>
        -
      </button>
      <button on:click={() =>{setOperation('multiply');}}>
        *
      </button>
      <button on:click={() =>{setOperation('divide');}}>
        /
      </button>
    </div>
  </div>
</div>

