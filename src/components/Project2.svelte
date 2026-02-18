<script>

    export let link;
    export let img = '/img/placeholder.svg';
    export let target='';

    export let projecttitle;
    export let projecthook = '';
    export let projectdesc = '';
    export let awardtext = '';

    

    $: projectClass = projecthook !== '' && projectdesc === '' 
        ? 'core' 
        : projecthook === '' && projectdesc !== '' 
        ? 'supplemental' 
        : '';
</script>

<a href="{link}" target="{target}">
    <div class="project-container {projectClass}" >
<!-- 
        {#if projectClass == 'core'}
        <img src={img} alt='' class="sidebar-item">
        {:else if projectClass == 'supplemental'}
        <div class="image-wrapper" style="background-image:url({img});">
             
        </div>
        {/if} -->

        <div class="img-wrapper img-wrapper-{projectClass}">
            {#if awardtext !== ''}
            <p class="award">{awardtext}</p>
            {/if}
            <img class="{projectClass}" src="{img}" alt="">
        </div>
        
        <div class="main-content {projectClass}">
            
            <p class="project-title">{projecttitle}</p>
            {#if projecthook !== ''}
            <p class="project-hook">{@html projecthook}</p>
            {:else if projectdesc !==''}
            <p class="project-desc">{projectdesc}</p>
            {/if}
        </div>
    </div>
</a>



<style>

    :root{
        --img-radius: 10px;
        --space: 10px;
    }

    .project-container {
        display: inline-flex;
        align-items: start; /* Align items to the top */
        gap: 1rem;
        transition: box-shadow var(--animationquick), border var(--animationquick), background-color var(--animationquick);
        background-color: var(--sand70);
        backdrop-filter: blur(5px);
        margin: var(--spacing4);
        gap: var(--space);
        padding: var(--space);
        border-radius: calc(var(--space) + var(--img-radius));
        box-shadow: 0px 0px 0px 1px var(--gray50);
    }

    .project-container:hover{
        box-shadow: 0px 0px 0px 3px  var(--gray50);
        background-color: var(--sand100);
    }

    .project-container > img {
        object-fit: cover;
        border-radius: 0;
        background-image: url("/img/placeholder.svg");
    }

    .core{
        flex-direction: row;
    }

    .supplemental{
        flex-direction: column;
    }

    .image-wrapper.core {
        height: stretch; /* Fill available height from grid */
        width: 100%;
        
        border-radius: 10px;
        overflow: clip;
        background-position: center;
        background-size: cover;
        flex-grow: 0;
        flex: 1;
    }

    .img-wrapper-core{
        height: stretch;
        width: 100%;
        aspect-ratio: 1/1;
    }

    .img-wrapper{
        position: relative;
        border-radius: var(--img-radius);
        overflow: clip;
    }

    .img-wrapper.core{
        height: stretch;
        width: 100%;
        aspect-ratio: 1/1;
    }

    img.core{
        height: stretch;
        object-fit: cover;
        max-height: 160px;
    }

    .img-wrapper.supplemental{
        height: 100%;
        width: 100%;
    }

    img.supplemental{
        height: 100%;
        object-fit: cover;
        max-height: 160px;
    }

    img{
        border-radius: 0;
    }

    
    


    .main-content.core {
        text-align: left;
        max-width: 270px;
    }

    .main-content.supplemental {
        text-align: left;
        max-width: 200px;
    }

    .award{
        position: absolute;
        padding: var(--spacing1) var(--spacing2);
        margin: 0;
        background: #e09122;
        background: linear-gradient(37deg,rgba(224, 145, 34, 1) 0%, rgba(186, 145, 50, 1) 39%, rgb(112, 76, 24) 53%, rgba(204, 146, 45, 1) 100%);
        background-size: 400% 400%;
        border-radius: 0px 0px var(--img-radius)  0px;
        color: rgb(255, 246, 213);
        font-weight: 600;
        font-size: 0.8rem;
        line-height: 100%;
    }

    @keyframes gradientAnimation{
        0% {
        background-position: 0% 0%; /* Start position */
        }
        50% {
            background-position: 200% 100%; /* Mid position */
        }
        100% {
            background-position: 0% 0%; /* End position, loops back to start */
        }
    }

    .project-container:hover .award{
        animation: gradientAnimation 3s ease-in-out infinite
    }

    .project-title{
        font-size: 1.2rem;
    }

    .project-hook{
        font-size: 1.6rem;
    }

    .project-desc{
        font-size: 1rem;
    }

    @media screen and (max-width: 500px) {
        .award{
            width: min-content;
        }
    }

    @media screen and (max-width: 400px) {
        .core{
            flex-direction: column;
        }

        .award{
            width: fit-content;
        }

    }


    
</style>