<script>
    import Project from "../components/Project.svelte";
    import Link from "../components/Link.svelte";
    import Footer from "../components/Footer.svelte";
    import Header from "../components/Header.svelte";
    import Avatar from "../components/Avatar.svelte";
    import Switch from "../components/Switch.svelte";

    import { fade, fly } from 'svelte/transition';

    let multiValue = "brand";

    function getRandomIntInclusive(min, max) {
        min = Math.ceil(min);
        max = Math.floor(max);
        return Math.floor(Math.random() * (max - min + 1)) + min; // The maximum is inclusive and the minimum is inclusive
    }

    let glassBG = getRandomIntInclusive(1,10);

</script>

<div class="landing" style="background-image: url('img/glass-bg/{glassBG}.webp')">
    <div class="left-col" style="background-image: url('img/horizontal-film-dithered.gif'); position:relative">
        <Avatar/>
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

<div class="gallery-container margin4">


<section class="toggle-container">
    <Switch bind:value={multiValue} label="" design="multi" options={['brand', 'product']} fontSize={12}/>
</section>

{#key multiValue}
<section class="main-gallery" out:fade={{ duration: 250 }}
        in:fly={{ y: 200, duration: 350, delay: 250 }} >
    {#if multiValue == "brand"}
    <div>
        <Project 
            link="/asucd"
            img="img/asucd/asucd-hero-image.svg"
            projecttitle="ASUCD"
            projecthook="Building a <span class='underline'>unified brand system</span> for UC Davis's largest student organization."
        />

        <Project
            link="/mental-health-initiative"
            img="img/mhi/mhi-hero-image-3.svg"
            projecttitle="Mental Health Initiative"
            projectdesc="Creative Direction • Merchandise, Social Media Campaign"
        />
    
    </div>

    <div>
        <Project
            link="/elections"
            img="img/elections/poster.avif"
            projecttitle="ASUCD Elections"
            projecthook="Revitalizing voter engagement with a <span class='underline'>clear, accessible</span> election <span class='underline'>marketing campaign.</span>"
        />
        <Project
            link="/sunset-fest-24"
            img="img/ssf24/Poster.avif"
            projecttitle="Sunset Fest 2024"
            projectdesc="Creative Direction • Integrated Advertising Campaign"
        />
    </div>

    <div>
        <Project
            link="/la-gran-tardeada"
            img="img/la-gran-tardeada/cover.svg"
            projecttitle="La Gran Tardeada"
            projectdesc="Creative Direction • Merchandise, Graphic Design"
        />
        <Project
            link="/mooseum"
            img="img/mooseum/67f2f56286b62a2ae012baae_P1088585.avif"
            projecttitle="Moo-vin' Moo-seum"
            projecthook="Transforming student awareness of campus resources through <span class='underline'>playful, story-driven design.</span>"
        />
        <Project
            link="/nu-alpha-kappa"
            img="img/nak/NAK-hero.svg"
            projecttitle="Nu Alpha Kappa Fraternity Inc."
            projectdesc="Creative Direction • Print & Social Media Campaigns"
        />
    </div>
    {:else if multiValue == "product"}
    <div>
        <Project
            link="/memorial-union"
            img="img/memorial-union/header.webp"
            projecttitle="Memorial Union App"
            projecthook="Building a <span class='underline'>data-informed navigation app</span> to help students find services faster and feel more connected on campus."
        />
    </div>

    <div>
        <Project 
            link="/applebttm"
            img="img/applebttm/header.webp"
            projecttitle="Applebttm"
            projecthook="Reinventing <span class='underline'>music discovery</span> through community, conversation, and <span class='underline'>clean UX.</span>"
        />
        <Project
            link='https://gyfigueroa.github.io/des157b/capstone/version2/index.html'
            img="img/project-covers/gorillai.webp"
            projecttitle='The GorillAI Problem'
            projectdesc="Interactive Narrative • HTML/CSS/Javascript"
            target="_blank"
        />
    </div>

    <div>
        <Project
            link='https://gyfigueroa.github.io/des157a/studio2/index.html'
            img="img/project-covers/everypicture.webp"
            projecttitle='Film Journal'
            projectdesc="Interactive Web Gallery • HTML/CSS"
            target="_blank"
        />
        <Project
            link='https://gyfigueroa.github.io/des157a/studio3/index.html'
            img="img/project-covers/pig.webp"
            projecttitle='Game of PIG'
            projectdesc="Interactive Web Game • HTML/CSS"
            target="_blank"
        />
        <Project
            link='https://iandunk.github.io/ECS163-Final-Project/index.html'
            img="img/project-covers/cinema.webp"
            projecttitle='Cinema Data Stories'
            projectdesc="Interactive Dashboard • D3.js"
            target="_blank"
        />
        <Project
            link='https://gyfigueroa.github.io/des157a/final/project/index.html'
            img="img/project-covers/madlibs.webp"
            projecttitle='Madlibs'
            projectdesc="Interactive Web App • HTML/CSS"
            target="_blank"
        />
    </div>
    {/if}
</section>
{/key}



</div>

<Footer/>


<style>


    .toggle-container{
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
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
        overflow-x: clip;
    }

    .landing > div {
        border-radius: var(--spacing5);
        
        background-position: center;
        background-size: cover;
    }

    .name-container{
        width: 100%;
    }
    
    .left-col{
        background-color: var(--sand50);
        box-shadow: 0px 0px 0px 1px var(--smoke50);
        backdrop-filter: blur(10px);
        z-index: 1;
    }

    .right-col{
        padding: var(--spacing5);
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        background-color: var(--forestgreen90);
        backdrop-filter: blur(10px);
        box-shadow: 0px 0px 0px 1px var(--smoke50)
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
        width: 100vw;
        overflow-x: clip;
    }

    .banner {
        width: 120vw;
        overflow: hidden;
        display: flex;
        background: brown;
        transform: rotate(-2deg);
        position: absolute;
        transform: translate(-5px, -50%) rotate(-2deg);
        z-index: 5;
        /* box-shadow: inset 0px 0px 30px 6px #452701;
        text-shadow: 0px -5px 15px orange, 0px 0px 3px #FF9800; */
        
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





