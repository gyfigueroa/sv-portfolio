<script>
    export let textHTML;
    export let wideimage = '';
    export let widealt = '';
    export let img = '';
    export let alt = '';
    export let img2 = '';
    export let alt2 = '';
    
    // Reactive variable for container class
    $: containerClass = img === '' ? 'single-column' : 'two-columns';
</script>

<div class="block-container {containerClass}">
    <div class="left-col">
        {@html textHTML}
        {#if wideimage !== ''}
            <img class="wideimg" src={wideimage} alt={widealt}>
        {/if}
    </div>
    {#if img !== ''}
    <div class="right-col">
        <img src={img} alt={alt}>
        {#if img2 !== ''}
            <img src={img2} alt={alt2}>
        {/if}
    </div>
    {/if}
</div>

<style>
    .block-container{
        display: grid;
        gap: var(--spacing4);
    }

    .single-column {
        grid-template-columns: 1fr;
        grid-template-rows: auto;
        
    }

    .two-columns {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto;
        gap: 0;
        
    }

    img{
        height: auto;
        border-radius: var(--spacing3);
    }

    .wideimg{
        margin-bottom: var(--spacing2);
    }

    @media screen and (min-width: 600px) {
        .two-columns {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: auto;
            gap: var(--spacing4);
        }
        
        /* Single column layout on desktop too if no image */
        .single-column {
            grid-template-columns: 1fr;
            grid-template-rows: auto;
        }
    }
</style>