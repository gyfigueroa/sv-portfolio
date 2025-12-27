<script>
    import Project from "../components/ProjectFlex2.svelte";
    import ProjectFlex from "../components/ProjectFlex2.svelte";
    import ProjectFlex2 from "../components/ProjectFlex2.svelte";
    import Hero from "../components/Hero.svelte";
    import Link from "../components/Link.svelte";
    import Footer from "../components/Footer.svelte";
    import TextBlock from "../components/TextBlock.svelte";
    import Emoji from "../components/Emoji.svelte";
    import Header from "../components/Header.svelte";
    import Saos from "saos";

    import Switch from "../components/Switch.svelte";

    import { fade, fly } from 'svelte/transition';

    let toggle = true;
    let toggleposition = 'left'
    let brandproject = 'visible';
    let productproject = 'hidden';

    let multiValue = "brand";


    function toggleVissible() {
        toggle = !toggle;
        if (toggle == true){
            brandproject = 'visible';
            productproject = 'hidden';
            toggleposition = 'left';
            
            document.documentElement.style.setProperty('--color1', "orange");
            document.documentElement.style.setProperty('--color2', "brown");
        } else {
            brandproject = 'hidden';
            productproject = 'visible';
            toggleposition = "right";
            document.documentElement.style.setProperty('--color1', "rgb(149, 255, 0)");
            document.documentElement.style.setProperty('--color2', "#002C21");
        }
    }
</script>

<div class="landing">
    <div class="left-col" style="background-image: url('img/horizontal-film-dithered.gif');">

    </div>
    <div class="right-col">
        <div class="name-container">
            <img src="img/GabrielFigueroa.svg" alt="">
            <div class="link-group">
                <Link
                    name="linkedin"
                />
                <Link
                    name="mail"
                />
            </div>
        </div>
        
        <div>
            <p class="hero-text">Designer & developer crafting intuitive, human-centered digital experiences.</p>
            <p class="hero-text">Former Project Manager @ ASUCD Creative Media.</p>
            <p class="hero-text">California-grown. Pistachio-fueled.</p>
        </div>
    </div>
</div>

<div class="banner-anchor">
    <div class="banner">
        <div class="group">
            <div class="banner-element hero-serif">Sel<i>e</i>c<i>t</i>ed</div>
            <div class="banner-element hero-serif"><i>W</i>ork</div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif">Se<i>l</i>ecte<i>d</i></div>
            <div class="banner-element hero-serif">W<i>o</i>r<i>k</i></div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif">Sele<i>c</i>ted</div>
            <div class="banner-element hero-serif">Wo <i>r</i>k</div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif">S<i>e</i>lec<i>t</i>ed</div>
            <div class="banner-element hero-serif"><i>W</i>ork</div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif"><i>S</i>electe<i>d</i></div>
            <div class="banner-element hero-serif">Wor<i>k</i></div>
            <div class="banner-element hero-serif">*</div>
        </div>

        <div aria-hidden=true class="group">
            <div class="banner-element hero-serif">Sel<i>e</i>c<i>t</i>ed</div>
            <div class="banner-element hero-serif"><i>W</i>ork</div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif">Se<i>l</i>ecte<i>d</i></div>
            <div class="banner-element hero-serif">W<i>o</i>r<i>k</i></div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif">Sele<i>c</i>ted</div>
            <div class="banner-element hero-serif">Wo <i>r</i>k</div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif">S<i>e</i>lec<i>t</i>ed</div>
            <div class="banner-element hero-serif"><i>W</i>ork</div>
            <div class="banner-element hero-serif">*</div>
            <div class="banner-element hero-serif"><i>S</i>electe<i>d</i></div>
            <div class="banner-element hero-serif">Wor<i>k</i></div>
            <div class="banner-element hero-serif">*</div>
        </div>    
    </div>
</div>

<Header/>

<div class="gallery-container">

<section class="toggle-container">
    <button class="toggle-wrapper label" on:click={toggleVissible}>
        Brand
        <div class="toggle">
            <div class="toggle-circle {toggleposition} skeu-effect">
            </div>
        </div>
        Product
    </button>
</section>

<section class="toggle-container">
    <Switch bind:value={multiValue} label="Choose a focus" design="multi" options={['brand', 'product']} fontSize={12}/>
    <p>
        Switch is {multiValue}
    </p>
</section>

{#if multiValue == "brand"}
<section class="main-gallery" in:fly={{ y: 200 }} out:fade>
    <div>

            <ProjectFlex2
                    link="/asucd"
                    img="img/asucd/asucd-hero-image.svg"
                    projecttitle="ASUCD"
                    projecthook="Building a unified brand system for UC Davis's largest student organization."
                />

            <ProjectFlex2
                link="/mental-health-initiative"
                img="img/mhi/mhi-hero-image-3.svg"
                projecttitle="Mental Health Initiative"
                projectdesc="Creative Direction- Merchandise, Social Media Campaign"
            />

            

    </div>
    
    <div>

            <ProjectFlex2
                link="/elections"
                img="img/elections/poster.avif"
                projecttitle="ASUCD Elections"
                projecthook="Revitalizing voter engagement with a clear, accessible election marketing campaign."
            />
            <ProjectFlex2
                link="/sunset-fest-24"
                img="img/ssf24/Poster.avif"
                projecttitle="Sunset Fest 2024"
                projectdesc="Creative Direction- Merchandise, Social Media Campaign"
            />
            

    </div>
    
    <div>
            <ProjectFlex2
                link="/la-gran-tardeada"
                img="img/la-gran-tardeada/cover.svg"
                projecttitle="La Gran Tardeada"
                projectdesc="Creative Direction- Merchandise, Social Media Campaign"
            />

            <ProjectFlex2
                link="/mooseum"
                img="img/mooseum/67f2f56286b62a2ae012baae_P1088585.avif"
                projecttitle="Moo-vin' Moo-seum"
                projecthook="Transforming student awareness of campus resources through playful, story-driven design."
            />
            <ProjectFlex2
                link="/nu-alpha-kappa"
                img="img/nak/NAK-hero.svg"
                projecttitle="Nu Alpha Kappa Fraternity Inc."
                projectdesc="Creative Direction- Merchandise, Social Media Campaign"
            />

            

    </div>
    
</section>
{/if}

{#if multiValue == "product"}
<section class="main-gallery" in:fly={{ y: 200 }} out:fade>
    <div>
        <ProjectFlex2
            link="/memorial-union"
            img="img/memorial-union/header.webp"
            projecttitle="Memorial Union App"
            projecthook="Building a data-informed navigation app to help students find services faster and feel more connected on campus."
        />
        
    </div>
    <div>
        <ProjectFlex2 
            link=""
            img="img/applebttm/header.webp"
            projecttitle="Applebttm"
            projecthook="Reinventing music discovery through community, conversation, and clean UX."
        />
        <ProjectFlex2
            link=''
            projecttitle='The Gorilla(i) Problem'
            projectdesc="Interactive Web App | HTML/CSS"
        />
    </div>
    
    <div>
        
        <ProjectFlex2
            link=''
            projecttitle='Game of PIG'
            projectdesc="Interactive Web App | HTML/CSS"
        />

        <ProjectFlex2
            link=''
            projecttitle='Film Industry Statistics'
            projectdesc="Interactive Web App | D3.js"
        />
        <ProjectFlex2
            link=''
            projecttitle='Madlibs'
            projectdesc="Interactive Web App | HTML/CSS"
        />

        
    </div>
</section>
{/if}

</div>

<Footer/>


<style>


    .toggle-container{
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
    }

    .toggle-wrapper{
        height: fit-content;
        display: flex;
        align-items: center;
        gap: var(--spacing2);
    }

    .toggle{
        height: 50px;
        width: 100px;
        border-radius: 50px;
        background-color: var(--sand100);
        background: linear-gradient(to top, var(--sand100, orange) 0%, var(--smoke, brown) 100%);
        display: flex;
        transition: all var(--animationquick);
        border: var(--spacing1) solid var(--sand100);
        position: relative;
    }

    .toggle-circle{
        height: 100%;
        aspect-ratio: 1/1;
        background-color: purple;
        border-radius: 100px;
        position: absolute;
        transition: all 0.5s ease;
    }

    .toggle-circle.left{
        left: 0;
        transform: translateX(0%);
        
    }
    .toggle-circle.right{
        left: 100%;
        transform: translateX(-100%);
        
    }

    .skeu-effect{
        background-color: green;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        background: linear-gradient(to top, var(--color1,orange) 0%, var(--color2,brown) 100%);
        box-shadow: inset 0px -2px 2px 1px var(--color2,brown), inset 0px 2px 2px 1px var(--color1,orange), 0px 5px 4px -2px rgba(0,0,0,0.5);
        position: relative;
        transition: all 0.5s;
    }

    .landing{
        width: 100vw;
        height: calc(100vh + 100px);
        background-image: url("img/glass.gif");
        background-position: center;
        background-size: cover;
        display: grid;
        grid-template-columns: auto;
        grid-template-rows: 1fr 1fr;
        padding: var(--spacing4) var(--spacing4) calc(var(--spacing4) + 100px) var(--spacing4) ;
        gap: var(--spacing4);
        color: var(--lime100);
    }

    .landing > div {
        border-radius: var(--spacing5);
        padding: var(--spacing5);
        background-position: center;
        background-size: cover;
    }

    .name-container{
        width: 100%;
    }

    .right-col{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        background-color: var(--forestgreen);
    }

    .gallery-container{
        min-height: 100vh;
    }
    .main-gallery{
        width: 100%;
        display: grid;
        grid-template-columns: 1fr;
        gap: var(--spacing4);
        padding: var(--spacing4);
    }

    .main-gallery > div {
        display: flex;
        flex-direction: column;
        gap: var(--spacing4);
    }

    .visible{
        animation: show var(--animationquick) ease-in-out forwards;
    }

    .hidden{
        display: none;
    }

    .gallery2{
        margin: var(--spacing4);
        min-width: auto;
        min-height: 100vh;
        position: relative;
        place-content: center;
        justify-items: center;
        text-align: center;
    }


    @media screen and (min-width: 600px) {
    /* CSS rules to apply when the screen width is 600px or less */
        .landing {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: auto;
        }

        .main-gallery{
            grid-template-columns: 1fr;
        }

    }

    @media screen and (min-width: 1000px) {
    /* CSS rules to apply when the screen width is 600px or less */
        .landing {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: auto;
        }

        .main-gallery{
            grid-template-columns: 1fr 1fr 1fr;
        }

    }

    /* SCROLLING BANNER STYLING */

    .banner-anchor{
        position: relative;
    }

    .banner {
        width: 120vw;
        overflow: hidden;
        display: flex;
        background: brown;
        transform: rotate(-2deg);
        position: absolute;
        transform: translate(0, -50%) rotate(-2deg);
        z-index: 5;
        
    }

    .banner-element {
        color: orange;
        padding: 20px 5px 10px;
        height: 70px;
        display: flex;
        align-items: center;
        justify-content: center;
        /* font-size: 40pt;
        font-family: "Yesteryear", cursive; */
    }

    .group{
        display: flex;
        will-change: transform; /* We should be nice to the browser - let it know what we're going to animate. */
        animation: scrolling 10s linear infinite;
    }

    @keyframes scrolling {
        0% {
        transform: translateX(0);
        }
        100% {
        transform: translateX(-100%);
        }
    }

    @keyframes -global-from-left {
    0% {
        transform: rotateX(50deg) translateX(-200vw) skewX(-50deg);
        opacity: 1;
    }
    100% {
        transform: rotateX(0deg) translateX(0) skewX(0deg);
        opacity: 1;
    }
    }



    @keyframes -global-show{
        0%{
            display: none;
        }
        1%{
            display: grid;
            opacity: 0;
            transform: translateY(50%);
        }
        100%{
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes hide{
        0%{
            opacity: 1;
            transform: translateY(0);
        }
        99%{
            opacity: 0;
            transform: translateY(100%);
            display: grid;
        }
        100%{
            display: none;
        }
    }

    /*********************/
    


</style>





