<script>
    export let label;
    export let id;

    export let min;
    export let max;

    import {createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();

    function changeMin(event) {

      const newMin = event.target.value;

      dispatch("update", {
        min: newMin,
        max: max
      })

      
    }
    function changeMax(event) {

       const newMax = event.target.value;

        dispatch("update", {
            min:min,
            max: newMax
        })
    }

</script>

<p>
  <label for={`${id}_min`}>{label} mínimo</label>
  <input type="range" min={0} max={50000} value={min} id={`${id}_min`} on:change={changeMin}>
    <span>{min}</span>
</p>

<p>
    <label for={`${id}_max`}>{label} máximo</label>
    <input type="range" min={0} max={50000} value={max} id={`${id}_max`} on:change={changeMax}>
    <span>{max}</span>
</p>