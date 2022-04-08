<script lang="ts">
    export let bwson_nblisteners_value: number = 0;
    export let bwson_bitrate_value: number = 0;
    export let bwson_result: number = 0;

    async function do_post() {
        const res = await fetch('https://scaw.sycured.com/bwserver', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                nblisteners: bwson_nblisteners_value,
                bitrate: bwson_bitrate_value
            })
        });

        const json = await res.json()
        bwson_result = json['result']
    }
</script>

<label>
    Number of listeners: <input type="number" bind:value={bwson_nblisteners_value} min=0>
</label>

<label>
    Bitrate (kb/s): <input type="number" bind:value={bwson_bitrate_value} min=0>
</label>

<button type="button" on:click={do_post}>Send</button>

<p>Server bandwidth (Mib/s): {bwson_result}</p>
