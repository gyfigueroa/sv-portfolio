<script>
    export let link = '#';
    export let img = '/img/placeholder.svg';
    export let alttext ='';
    export let target='';
    export let role1='';
    export let role2='';
    export let category=''
    export let addywinner=''

    export let projecttitle;
    export let projecthook = '';
    export let projectdesc = '';
    

</script>

<a href="{link}" target="{target}">
    <div class="project-container">

        <div class="img-wrapper">
            <div class="tags">
                

                {#if category !== ''}
                    {#if addywinner === 'true'}
                        <p class="tag firstof addy">ADDY® Winner</p>
                        <p class="tag {category}">{category}</p>
                    {:else if target !== ""}
                        <p class="tag firstof external">External <img class="icon" src="img/link-arrow.svg" style="display:inline" alt=""></p>
                        <p class="tag {category}">{category}</p>
                    {:else}
                        <p class="tag firstof {category}">{category}</p>
                    {/if}
                {/if}
                
            </div>
            <img class="" src="{img}" alt="{alttext}">
        </div>
        
        <div class="text-wrapper">
            <p class="project-title">{projecttitle}</p>
            {#if projecthook !== ''}
                <p class="project-hook">{@html projecthook}</p>
            {:else if projectdesc !==''}
                <p class="project-desc">{projectdesc}</p>
            {/if}

            <div class="roles">
                {#if role1 !== ''}
                    <p class="role mono">{role1}</p>
                {/if}

                {#if role2 !== ''}
                    <p class="role mono">{role2}</p>
                {/if}
            </div>
        </div>
    </div>
</a>

<style>

    .img-border2{
        border-radius: 0px;
        border-image: url("/img/border.svg") 21 / 10px / 9px round;
        
    }

    .project-container{
        padding: var(--spacing2);
        display: flex;
        flex-direction: column;
        gap: var(--spacing2);
        transition: background 0.5s ease, transform 0.5s ease;
    }

    .project-container:hover{
        background-color: var(--forestgreen5, rgba(25, 47, 25, 0.1));
    }

    .project-container:hover .role{
        opacity: 100%;
    }

    .img-wrapper{
        display: flex;
        flex-direction: column;
        gap: 0px;
    }

    .tags{
        display: flex;
        flex-direction: row;
        transform-origin: bottom;
        /* z-index: -1; */
    }

    .tag{
        font-family: var(--ffmono);
        line-height: 1em;
        font-weight: 500;
        font-size: 1rem;
        padding: 0.1em 0.5em 0.1em 1.25em;
        padding: 0.1em 0.5em;
        margin-left: -0.25em;
        margin-top: 0px;
        margin-bottom: 0px;
        background-color: gray;
        border: 1px solid lightgray;
        border-radius: 0.5em 0.5em 0px 0px;
        

    }

    .tag.firstof{
        padding: 0.1em 0.5em;
        margin-left: 0px;
        z-index: 1;
    }

    .brand{
        text-transform: capitalize;
    /*     font-weight: 800; */
        background: linear-gradient(222deg, #E0399A, #BA0D69); 
        box-shadow: inset 0px -3px 0px #E0399A;
        border: 1px solid #b12677;
        color: #FFDAFD;
    
    }

    .product{
        text-transform: capitalize;
        background: linear-gradient(222deg, #39bee0, #0dbaba); 
        box-shadow: inset 0px -3px 0px #39bee0;
        border: 1px solid #26a8b1;
        color: #dafffe;
    }

    .external{
        text-transform: capitalize;
        background: linear-gradient(222deg, var(--midgreen), var(--forestgreen)); 
        box-shadow: inset 0px -3px 0px var(--midgreen);
        border: 1px solid var(--forestgreen50);
        color: var(--lime100);
    }

    .addy{
        background: linear-gradient(37deg,rgba(224, 145, 34, 1) 0%, rgba(186, 145, 50, 1) 39%, rgb(112, 76, 24) 53%, rgba(204, 146, 45, 1) 100%);
        background-size: 400% 400%;
        color: #FFF8DA;
        box-shadow: inset 0px -3px 0px #DDA326;
        border: 1px solid #a97507;
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

    .project-container:hover .addy{
        animation: gradientAnimation 3s ease-in-out infinite
    }

    img{
        border-radius: 0px ;
    }

    .text-wrapper{
        display: flex;
        flex-direction: column;
        gap: var(--spacing2);
    }

    .text-wrapper > *{
        margin: 0;
    }

    .project-hook{
        margin-bottom: var(--spacing2);
    }

    .project-desc{
        line-height: 1em;
    }

    .roles{
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: var(--spacing1);
    }

    .role{
        border: 1px solid var(--forestgreen);
        margin: 0px;
        padding: 2px 12px;
        border-radius: 20px;
        opacity: 30%;
        transition: all 1s ease;
    }
</style>