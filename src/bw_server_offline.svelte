<script lang="ts">
    export let bwsof_nblisteners: number = 0;
    export let bwsof_bitrate: number = 0;
</script>

<label>
    Number of listeners: <input type="number" bind:value={bwsof_nblisteners} min=0>
</label>

<label>
    Bitrate (kb/s): <input type="number" bind:value={bwsof_bitrate} min=0>
</label>

<p>Server bandwidth (Mib/s): {125 * bwsof_nblisteners * bwsof_bitrate / 128 || 0}</p>
