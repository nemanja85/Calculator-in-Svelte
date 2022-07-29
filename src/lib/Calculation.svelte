<script>
  let total = 0;
  let state = null;
  let console = '';

  function resolveState(){
    switch(state){
      case "add":
        total += parseFloat(console);
        console="0";
        break;
      case "substract":
        total -= parseFloat(console);
        console="0";
        break;
      case "multiply":
        total *= parseFloat(console);
        console="0";
        break;
      case "divide":
        total += parseFloat(console);
        console="0";
        break;
      default:
      total = parseFloat(console);
        console="0";
        break;
    }

  }
  function setOperation(operation){
    resolveState();
    state = operation;
  }
  function setValues(value){
      if(console.toString() == '' || state == 'equal') {
          console = '';
      }
      if(state == 'equal'){
        state = null;
      }
      if(value == 'C'){
        total = 0;
        state = null;
        console = '';
        return;
      }
      console = console + value;
  }
  function equal(){
    resolveState();
    console = total;
    state = "equal"
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
    <div class="numbers">
      <div class="section">
        <button on:click={()=>{setValues(7)}}>7</button>
        <button on:click={()=>{setValues(8)}}>8</button>
        <button on:click={()=>{setValues(9)}}>9</button>
      </div>
      <div class="section">
        <button on:click={()=>{setValues(6)}}>6</button>
        <button on:click={()=>{setValues(5)}}>5</button>
        <button on:click={()=>{setValues(4)}}>4</button>
      </div>
      <div class="section">
        <button on:click={()=>{setValues(3)}}>3</button>
        <button on:click={()=>{setValues(2)}}>2</button>
        <button on:click={()=>{setValues(1)}}>1</button>
      </div>
      <div class="section">
        <button on:click={()=>{setValues(0)}}>0</button>
        <button on:click={()=>{setValues('.')}}>.</button>
        <button on:click={()=>{setValues('C')}}>C</button>
      </div>
    </div>
    <div class="equal">
      <button on:click={equal}>=</button>
    </div>
  </div>
</div>

