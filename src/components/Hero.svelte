<script>
    import Link from "./Link.svelte";

    export let category;
    export let title;

    export let role;
    export let names;

    export let role2='';
    export let names2='';

    export let role3='';
    export let names3='';

    export let role4='';
    export let names4='';

    export let role5='';
    export let names5='';

    export let text = '';
    export let text2 = '';
    export let text3 = '';
    export let img;

    export let link = '';
    export let linktext = '';

</script>

<div class="hero-container">
    <div class="img-container">
        <img src="{img}" alt="">
    </div>
    <!-- <div class="spacer"></div> -->
    <div class="content">
        <div class="project-details" >
            <div class="left-content">
                <p class="label">{category}</p>
                <p class="hero-title">{title}</p>
                <div class="credit">
                    <p class="mono label-outline label-white">{role}</p>
                    <p class="hero-text">{names}</p>
                </div>
                {#if role2 !== ''}
                <div class="credit">
                    <p class="mono label-outline label-white">{role2}</p>
                    <p class="hero-text">{names2}</p>
                </div>
                {/if}

                {#if role3 !== ''}
                <div class="credit">
                    <p class="mono label-outline label-white">{role3}</p>
                    <p class="hero-text">{names3}</p>
                </div>
                {/if}

                {#if role4 !== ''}
                <div class="credit">
                    <p class="mono label-outline label-white">{role4}</p>
                    <p class="hero-text">{names4}</p>
                </div>
                {/if}

                {#if role5 !== ''}
                <div class="credit">
                    <p class="mono label-outline label-white">{role5}</p>
                    <p class="hero-text">{names5}</p>
                </div>
                {/if}
            </div>
            <div class="right-content">
                {#if text !== ''}
                <p class="hero-text">{text}</p>
                {/if}
                {#if text2 !== ''}
                <p class="hero-text">{text2}</p>
                {/if}
                {#if text3 !== ''}
                <p class="hero-text">{text3}</p>
                {/if}

                
                {#if link !== '' && linktext !== ''}
                <Link link="{link}" linktext="{linktext}" transparency='no'/>
                {/if}
                
            </div>
        </div>
    </div>
    
</div>

<style>
    .hero-container{
    }

    /* .hero-container::after{
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        backdrop-filter: blur(20px) contrast(1.25) brightness(0.9);
        mask-image: linear-gradient(to top,black 10px, transparent 30px);
        -webkit-mask-image: linear-gradient(to bottom, transparent calc(100vh - 100px), black calc(100vh + 100px));
        pointer-events: none;
    } */

    .hero-container::-webkit-scrollbar { /* WebKit */
        width: 0;
        height: 0;
    }

    .img-container{
        position: sticky;
        top: 0;
        width: 100vw;
        height: 100vh;
        z-index: -2;
    }


    .img-container img {
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 0;
    }


    .content{
        padding: var(--spacing4);
        position: relative;
    }

    .content::after{
        content: '';
        position: absolute;
        width: 100%;
        height: 120%;
        bottom: 0;
        left: 0;
        backdrop-filter: blur(20px) saturate(1.75) brightness(0.8);
        mask-image: linear-gradient(to top, black 10px, transparent 30px);
        -webkit-mask-image: linear-gradient(to bottom, transparent, black 20%);
        pointer-events: none;
    }

    .project-details{
        width: auto;
        /* background-color: blue; */
        background: var(--sand25);
        backdrop-filter: blur(20px) brightness(0.9) saturate(1.5);
        box-shadow: 0px 0px 0px 1px var(--smoke50);
        /* margin: var(--spacing4); */
        padding: var(--spacing5);
        border-radius: var(--spacing5);
        display: grid;
        grid-template-columns: auto;
        grid-template-rows: auto; /* Single row */
        color: var(--sand100);
        gap: var(--spacing4);
        position: relative;
        z-index: 3;
    }

    .credit {
        margin-top: var(--spacing3);
        display: flex;
        gap: var(--spacing1);
        flex-wrap: wrap;
        align-items: baseline;
    }

    .credit > *{
        margin:0;
    }

    @media screen and (min-width: 600px) {
    /* CSS rules to apply when the screen width is 600px or less */
        .project-details {
            grid-template-columns: 1fr 1fr;
        }
    }
</style>