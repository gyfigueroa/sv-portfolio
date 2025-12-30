<script>
    export let name = '';
    export let link = '';
    export let linktext = '';
    export let transparency = '';
</script>

{#if name == ''}
<a class="link hero-text {transparency}" href="{link}" target="_blank">{linktext}
    <img class="icon" src="img/link-arrow.svg" alt="">
</a>
{/if}

{#if name == "linkedin"}
    <a class="link hero-text" href="https://www.linkedin.com/in/gabriel-figueroa-780b62245/" target="_blank">LinkedIn
        <img class="icon" src="img/link-arrow.svg" alt="">
    </a>
{/if}

{#if name == "mail"}
    <a class="link hero-text" href="&#109;&#97;&#105;&#108;&#116;&#111;&#58;%67%79%66%69%67%75%65%72%6F%61%40%63%6F%78%2E%6E%65%74">Mail
        <img class="icon" src="img/link-arrow.svg" alt="">
    </a>
{/if}

<style>
    .link{
        display: inline-flex;
        align-items: center;
        gap: var(--spacing1);
        padding:  var(--spacing1) var(--spacing2);
        border-radius: var(--spacing2);
        background-color: var(--lime20);
        backdrop-filter: blur(5px);
        color: var(--lime100);
        transition: background-color var(--animationquick), gap var(--animationquick);
    }

    .link:hover{
        background-color: var(--lime50);
        /* gap: var(--spacing2); */
    }

    .no{
        background-color: #1F5526;
    }

    .no:hover{
        background-color: #4B9624;
    }

    .icon{
        transition: margin var(--animationquick);
        border-radius: 0;
    }

    .link:hover > .icon{
        margin-bottom: 5px;
    }


</style>