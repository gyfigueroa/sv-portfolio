<script>
    export let link;
    export let img = 'img/placeholder.svg';

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
        {#if projectClass == 'core'}
        <img src={img} alt='' class="sidebar-item">
        {:else if projectClass == 'supplemental'}
        <div class="image-wrapper" style="background-image:url({img});">
            
        </div>
        {/if}
        
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
        display: flex;
        align-items: start; /* Align items to the top */
        gap: 1rem;
        transition: box-shadow var(--animationquick);
    /*     margin: var(--spacing2); */
        /* max-width: 500px; */
    }

    .core{
        flex-direction: column;
    }

    .supplemental{
        flex-direction: row;
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
        flex: 1;
    }


    .main-content {
        text-align: left;
        flex-grow: 1;
        flex: 2;
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