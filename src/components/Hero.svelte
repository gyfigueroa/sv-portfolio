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

<div class="hero-container" style="background-image: url({img});">
    <div class="spacer"></div>
    <div class="project-details" >
        <div class="left-content">
            <p class="label">{category}</p>
            <p class="hero-title">{title}</p>
            <div class="credit">
                <p class="label">{role}</p>
                <p class="hero-text">{names}</p>
            </div>
            {#if role2 !== ''}
            <div class="credit">
                <p class="label">{role2}</p>
                <p class="hero-text">{names2}</p>
            </div>
            {/if}

            {#if role3 !== ''}
            <div class="credit">
                <p class="label">{role3}</p>
                <p class="hero-text">{names3}</p>
            </div>
            {/if}

            {#if role4 !== ''}
            <div class="credit">
                <p class="label">{role4}</p>
                <p class="hero-text">{names4}</p>
            </div>
            {/if}

            {#if role5 !== ''}
            <div class="credit">
                <p class="label">{role5}</p>
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

            <!-- <p class="hero-text">{text}</p>
            {#if link !== '' && linktext !== ''}
            <Link link="{link}" linktext="{linktext}"/>
            {/if} -->
            
        </div>
    </div>
</div>

<style>
    .hero-container{
        width: 100vw;
        height: 100vh;
        background-image: url("img/placeholder.svg");
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        position: sticky;
        bottom: 0;
        overflow: scroll;
        overflow-y: scroll;
        scrollbar-width: none; /* Firefox */
        -ms-overflow-style: none;  /* Internet Explorer 10+ */
    }

    .hero-container::-webkit-scrollbar { /* WebKit */
        width: 0;
        height: 0;
    }

    .spacer{
        height: 100vh;
        width: 100px;
        /* border: 1px red solid; */
    }
    .project-details{
        width: auto;
        /* background-color: blue; */
        backdrop-filter: blur(400px) saturate(2);
        box-shadow: 0px 0px 0px 1px var(--smoke50);
        margin: var(--spacing4);
        padding: var(--spacing5);
        border-radius: var(--spacing5);
        display: grid;
        grid-template-columns: auto;
        grid-template-rows: auto; /* Single row */
        color: var(--sand100);
        gap: var(--spacing4);
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