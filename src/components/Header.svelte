
<a href="/">
    <header>
        <img class="home-icon" src="img/home.svg" alt="">
        <p class="hero-serif">G<i>a</i>br<i>i</i>el Fig<i>u</i>er<i>o</i>a</p>
    </header>
</a>


<style>
    header{
        border-radius: var(--spacing5);
        background-color: var(--forestgreen);
        color: var(--lime100);
        padding-left: 15px;
        display: inline-flex;
        gap: 30px;
        justify-content: flex-start;
        align-items: center;
        width: 50px;
        height: 50px;
        overflow: hidden;
        position: sticky;
        left: var(--spacing4);
        top: var(--spacing4);
        z-index: 1;
        transition: all var(--animationquick) ease;
        margin: var(--spacing2);
    }

    header:hover{
        width: 220px;
        /* height: calc(2 * var(--spacing5)); */
        transform-origin: top left;
        transform: scale(1.25);
        gap: var(--spacing2);
        padding: 0px 25px;
    }

    header p {
        font: var(--heroserif);
        letter-spacing: -1.5px;
        font-size: 18pt;
        white-space: nowrap
    }

    .home-icon{
        height: 20px;
        width: auto;
        transition: all var(--animationquick);
        border-radius: 0;
    }

    header:hover > .home-icon{
        transform: rotate(-90deg);
    }

    
</style>