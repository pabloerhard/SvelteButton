<script>
  let count = 0;
  const increment = () =>{
      count+=1
  }
</script>

<h1>{count}</h1>
<button on:click={increment} >
Increment
</button>

<style>
  button {
    padding:15px 20px;

  }
</style>

