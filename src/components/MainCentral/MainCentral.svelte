<script lang="ts">
    import Tile from '../Tile/Tile.svelte';
    import AccumulationPrecipitation32 from "carbon-icons-svelte/lib/AccumulationPrecipitation32";
    import { onDestroy, onMount } from 'svelte';

    const random = (length = 8) => {
        let chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';

        let str = '';
        for (let i = 0; i < length; i++) {
            str += chars.charAt(Math.floor(Math.random() * chars.length));
        }

        return str;
    };

    let interval;
    let randomString = random(500);

    onMount(async () => {
        interval = setInterval(() => {
            randomString = random(500);
        }, 500);
    });

    onDestroy(() => {
        clearInterval(interval);
    });
</script>

<div class="central-grid center-absolute">
    <Tile rowStart="1" rowEnd="4" columnStart="1" columnEnd="4" >
        Coffee in old town Sarajevo, the historic site, where thousands of locals have come to enjoy the special drinks, the atmosphere, the beautiful old town buildings and the culture and history.
        The area has been a gathering place since the 19th century. There are many old buildings, many museums, several galleries, theaters, concerts, exhibitions and many other interesting things.
    </Tile>
    <Tile rowStart="1" rowEnd="3" columnStart="4" columnEnd="6" >
        <div class="bordered-div">
            <div class="bordered-div">
                <div class="bordered-div"></div>
            </div>
        </div>
    </Tile>
    <Tile rowStart="3" rowEnd="3" columnStart="4" columnEnd="6" ><AccumulationPrecipitation32 /></Tile>
    <Tile rowStart="4" rowEnd="6" columnStart="1" columnEnd="6" >
        {#if !!randomString}
            <div class="random-string-container">{randomString}</div>
        {/if}
    </Tile>
</div>

<style>
    .central-grid {
        display: grid;
        width: 500px;
        height: 500px;
        grid-template-columns: 20% 20% 20% 20% 20%;
        grid-template-rows: 20% 20% 20% 20% 20%;
        grid-gap: 10px;
    }

    .center-absolute {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    .random-string-container {
        line-break: anywhere;
        text-align: center;
    }

    .bordered-div {
        border: 1px solid #EDEFFD;
        margin: 5px;
        height: 100%;
        width: 100%;
        box-sizing: border-box;
    }
</style>