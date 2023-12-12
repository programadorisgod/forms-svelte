<script>
    export let id;
    export let value;
    export let label;
</script>

<p>
    <label for={id}>{label}</label>
      <input id={id} type="text" bind:value>
</p>