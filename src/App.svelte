<script>
  import Input from "../Input.svelte";
  import Drowdown from "./Drowdown.svelte";
  import Ranges from "./Ranges.svelte";

 let state = {
    name: 'John',
    age: 42,
    sector: 'IT',
    salary: {
      min: 15000,
      max: 35000
    }
  };

  let Sectors = ['Backend', 'Frontend', 'IT', 'QA', 'DevOps']
  let error = false;
  function sendData(event) {
    alert(JSON.stringify(state));
  }

  function updateSalary(event) {
    if (event.detail.min > event.detail.max) {
       alert("Min salary can't be greater than max salary");
       error = true
    }else{
      state.salary = event.detail;
      error = false
    }

  }
 
</script>


<main>

  <form on:submit|preventDefault={sendData}>

    <Input id="name" bind:value={state.name} label="Name" />
    <Input id="age" bind:value={state.age} label="Age" />
    <Drowdown id="sector" bind:value={state.sector} label="Sector" options={Sectors} />
    
    <Ranges id="salary" max={state.salary.max} min={state.salary.min} label="Salary"  on:update={updateSalary}/>

     <p>
      <input type="submit" value="Enviar" disabled={error}> 
    </p>

  </form>
  
</main>








<style>
  
</style>
