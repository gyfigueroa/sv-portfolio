<script>
    export let link;
    export let img;
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
        <div class="image-wrapper" style="background-image:{img}; aspect-ratio: {aspectratio}"><!-- 
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
        display: inline-grid;
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
        grid-template-columns: auto auto; /* Auto for image, 1fr for text */
        grid-template-rows: auto; /* Single row */
    }

    .supplemental{
        grid-template-columns: 200px;
        gap: 0;
    }

    .image-wrapper {
        display: flex;
        align-items: start; /* Align image to top */
        height: 100%; /* Fill available height from grid */
        aspect-ratio: 1/1;
        border-radius: 10px;
        overflow: clip;
        background-color: gray;
        background-image: url(img/placeholder.svg);
        background-position: center;
        background-size: cover;
    }

    .sidebar-item {
        height: 100%; /* Fill the wrapper height */
        /* width: auto; /* Maintain aspect ratio */ 
        max-height: 100%; /* Prevent overflow */
        object-fit: cover;
        display: block;
    }

    .main-content {
        max-width: 400px;
        text-align: left;
        /* This dictates the grid row height */
    }

</style>