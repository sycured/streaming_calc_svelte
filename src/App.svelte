<script lang="ts">
    import {Tabs, Tab, TabList, TabPanel} from 'svelte-tabs';
    import Bw_server_offline from './bw_server_offline.svelte';
    import Server_usage_bw_offline from './server_usage_bw_offline.svelte';
    import Bw_server_online from './bw_server_online.svelte';
    import Server_usage_bw_online from './server_usage_bw_online.svelte';
</script>

<main>
    <h1>SCHY</h1>

    <Tabs>
        <TabList>
            <Tab>bw_server - offline</Tab>
            <Tab>server_usage_bw - offline</Tab>
            <Tab>bw_server - online</Tab>
            <Tab>server_usage_bw - online</Tab>
        </TabList>

        <TabPanel>
            <Bw_server_offline/>
        </TabPanel>

        <TabPanel>
            <Server_usage_bw_offline/>
        </TabPanel>

        <TabPanel>
            <Bw_server_online/>
        </TabPanel>

        <TabPanel>
            <Server_usage_bw_online/>
        </TabPanel>
    </Tabs>
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: dodgerblue;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
