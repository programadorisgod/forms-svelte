<script>
    export let id;
    export let value;
    export let label;
    export let options;


</script>

<p>
    <label for={id}>{label}</label>
    <select  id={id} bind:value>
        {#each options as option}
            <option value={option}>{option}</option>
         {/each}
    </select>
</p>