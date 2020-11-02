<script lang="ts">
    export let subwof_nblisteners: number = 0;
    export let subwof_bitrate: number = 0;
    export let subwof_nbdays: number = 0;
    export let subwof_nbhours: number = 0;
</script>

<label>
    Number of listeners: <input type="number" bind:value={subwof_nblisteners} min=0>
</label>

<label>
    Bitrate (kb/s): <input type="number" bind:value={subwof_bitrate} min=0>
</label>

<label>
    Number of days: <input type="number" bind:value={subwof_nbdays} min=0>
</label>

<label>
    Number of hours by days: <input type="number" bind:value={subwof_nbhours} min=0 max=24>
</label>

<p>
    Bandwidth used (GiB):
    {28125 * subwof_nbdays * subwof_nbhours * subwof_bitrate * subwof_nblisteners / 65536 || 0}
</p>
