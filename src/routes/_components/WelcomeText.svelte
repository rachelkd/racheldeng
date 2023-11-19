<script>
    import SvgIcon from '@jamescoyle/svelte-icon';
    import { mdiArrowLeftBottom } from '@mdi/js';
    // import { flip } from "svelte/animate";
    
    export let showSummary = false;
    export let handleClick;
    let showArrow = false;

    function toggleShowArrow() {
        showArrow = !showArrow;
    }
    // let scroll = 0;
</script>

<div class="welcome">
    <div class="welcome-text-box">
        <h1>nice to meet you!<br>my name is <span class=highlight>rachel</span>.</h1>
    </div>
    {#if !showSummary}
    <div class="enter-prompt">
        <button id="start-btn" on:mouseenter={toggleShowArrow} on:mouseleave={toggleShowArrow} on:click={() => handleClick("start-btn")}><p>press enter or click here&nbsp;</p>{#if showArrow}<SvgIcon type="mdi" path={mdiArrowLeftBottom} />{/if}</button>
    </div>
    {/if}
</div>

<style>
    #start-btn {
        display: flex;
        align-items: center;
        justify-content: left;
    }
</style>