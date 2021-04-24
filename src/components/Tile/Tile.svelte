<script lang="ts">
    export let rowStart: number;
    export let rowEnd: number;
    export let columnStart: number;
    export let columnEnd: number;
</script>

<div class="tile" style="grid-row-start: {rowStart}; grid-row-end: {rowEnd}; grid-column-start: {columnStart}; grid-column-end: {columnEnd}">
    <slot></slot>
</div>

<style>
    .tile {
        background-color: #1c3041;
        color: #EDEFFD;
        height: 100%;
        width: 100%;
        border-radius: 20px;
        padding: 15px 25px;
        box-sizing: border-box;
        font-size: 17px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>