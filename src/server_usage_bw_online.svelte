<script lang="ts">
    export let subwon_nblisteners_value: number = 0;
    export let subwon_bitrate_value: number = 0;
    export let subwon_nbdays_value: number = 0;
    export let subwon_nbhours_value: number = 0;
    export let subwon_result: number = 0;

    async function do_post() {
        const res = await fetch('https://schy.sycured.com/serverusagebw', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                nblisteners: subwon_nblisteners_value,
                bitrate: subwon_bitrate_value,
                nbhours: subwon_nbhours_value,
                nbdays: subwon_nbdays_value
            })
        });

        const json = await res.json()
        subwon_result = json['result']
    }
</script>

<label>
    Number of listeners: <input type="number" bind:value={subwon_nblisteners_value} min=0>
</label>

<label>
    Bitrate (kb/s): <input type="number" bind:value={subwon_bitrate_value} min=0>
</label>

<label>
    Number of days: <input type="number" bind:value={subwon_nbdays_value} min=0>
</label>

<label>
    Number of hours by days: <input type="number" bind:value={subwon_nbhours_value} min=0 max=24>
</label>

<button type="button" on:click={do_post}>Send</button>

<p>Bandwidth used (GiB): {subwon_result}</p>
