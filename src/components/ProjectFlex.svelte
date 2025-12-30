<script>
    import { fade, fly } from 'svelte/transition';
    
    export let link;
    export let img = 'img/placeholder.svg';
    export let aspectratio = '1/1';
    export let projecttitle;
    export let projecthook = '';
    export let projectdesc = '';

    $: projectClass = projecthook !== '' && projectdesc === '' 
        ? 'core' 
        : projecthook === '' && projectdesc !== '' 
        ? 'supplemental' 
        : '';</script>

<a href="{link}">
    <div class="project-container {projectClass}">
        <div class="image-wrapper" style="background-image:url({img}); aspect-ratio: {aspectratio}"><!-- 
            <img src={img} alt={alttext} class="sidebar-item"> -->
        </div>
        
        <div class="main-content">
            <p class="project-title">{projecttitle}</p>
            {#if projecthook !== ''}
            <p class="project-hook">{projecthook}</p>
            {:else if projectdesc !==''}
            <p class="project-desc">{projectdesc}</p>
            {/if}
        </div>
    </div>
</a>


<style>
    .project-container {
        display: inline-flex;
        align-items: start; /* Align items to the top */
        gap: 1rem;
        transition: box-shadow 0.5s;
        margin: var(--spacing2);
        /* max-width: 500px; */
    }

    .project-container:hover{
        box-shadow: 0px 0px 0px var(--spacing2) var(--sand50);
    }

    .core{
        flex-direction: row;
    }

    .supplemental{
        flex-direction: column;
        max-width: 200px;
    }

    .image-wrapper {
        height: 100%; /* Fill available height from grid */
        width: 100%;
        aspect-ratio: 1/1;
        border-radius: 10px;
        overflow: clip;
        background-position: center;
        background-size: cover;
        flex-grow: 0;
    }

    .sidebar-item {
        height: 100%; /* Fill the wrapper height */
        /* width: auto; /* Maintain aspect ratio */ 
        max-height: 100%; /* Prevent overflow */
        object-fit: cover;
        display: block;
    }

    .main-content {
        text-align: left;
        flex-grow: 1;
        /* This dictates the grid row height */
    }

    @media screen and (max-width: 600px) {
    /* CSS rules to apply when the screen width is 600px or less */
      .core{
        flex-direction: column;
        max-width: none;
      }
    }
</style>