<script>
    import Project from "../components/Project.svelte";
    import Project2 from "../components/Project2.svelte";
    import ProjectNew from "../components/ProjectNew.svelte";
    import Item from "../components/Item.svelte";
    import Link from "../components/Link.svelte";
    import Footer from "../components/Footer.svelte";
    import Header from "../components/Header.svelte";
    import Avatar from "../components/Avatar.svelte";
    import Switch from "../components/Switch.svelte";
    import { onMount } from "svelte";

    import { fade, fly } from 'svelte/transition';

    let multiValue = "brand";

    function getRandomIntInclusive(min, max) {
        min = Math.ceil(min);
        max = Math.floor(max);
        return Math.floor(Math.random() * (max - min + 1)) + min; // The maximum is inclusive and the minimum is inclusive
    }

    let glassBG;

    onMount(() => {
        glassBG.style.backgroundImage= `url('img/glass-bg/${getRandomIntInclusive(1, 10)}.webp')`
    })

    import { gsap } from 'gsap/dist/gsap';
    // For plugins, e.g., ScrollTrigger
    import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

    if (typeof window !== "undefined") {
        gsap.registerPlugin(ScrollTrigger);
    }

    let context;
    let banner;

    let view = 'brand';
    

    onMount(() => {

        console.log('var view: ', view);
        if (typeof window !== "undefined") {
            gsap.registerPlugin(ScrollTrigger);
        }

        const ctx = gsap.context((self) => {
            const elements = gsap.utils.toArray('.aos')
            console.log(elements)
            elements.forEach((element, i) => {
                gsap.from(element, {
                    scrollTrigger: {
                        trigger: element,
                        start: 'top bottom-=100',
                        markers: false,
                    },
                    y: 100,
                    opacity:0,
                    
                })
            })

        }, context);

        gsap.to(banner,{
            scrollTrigger:{
                trigger: banner,
                start: "top bottom",
                end: 'bottom top',
                markers: false,
                scrub: 1,
            },
            x: -1000,
        })


    return () => ctx.revert(); // <- Cleanup!
  });
    
    

</script>

<svelte:head>
    <title>Gabriel Figueroa Design</title>
</svelte:head>

<div class="landing" bind:this={glassBG}>
    <div class="left-col" style="background-image: url('img/horizontal-film-dithered.gif'); position:relative">
        <Avatar img="img/Headshot.jpg" />
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
            <p class="hero-text">Currently designing at Bodewell Group.</p>
            <p class="hero-text">California-grown. Pistachio-fueled.</p>
        </div>
    </div>
</div>

<!-- <div class="banner-anchor">
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
</div> -->

<div class="banner-container">
    <div class="banner-anchor-2">
        <div class="banner2" bind:this={banner}>
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
            <div class="banner-element hero-serif">Sel<i>e</i>c<i>t</i>ed</div>
            <div class="banner-element hero-serif"><i>W</i>ork</div>
            <div class="banner-element hero-serif">*</div>

        </div>
    </div>

</div>



<div class="grid-bg">



<Header/>

<div class="gallery-container margin4">


<!-- <section class="toggle-container" style="margin-top: 60px">
    <Switch bind:value={multiValue} label="" design="multi" options={['brand', 'product']} fontSize={12}/>
</section> -->



<div class="grid-gallery" style="min-height: 100vh;" bind:this={context}>
    <div class="section button-wrapper">
        <!-- <p  class="label" style="margin: auto; position:absolute">viewing</p> -->
        
        <label class="button-container" id="brand-button">
            <input type="radio" checked="checked" name="radio" bind:group={view} value="brand">
            <div class="tag-button">Brand</div>
            <span class="checkmark"></span>
        </label>

        <label class="button-container" id="product-button">
            <input type="radio" name="radio" bind:group={view} value='product'>
            <div class="tag-button">Product</div>
            <span class="checkmark"></span>
        </label>
    </div>

    {#key view}
    <div out:fade={{ duration: 250 }}
        in:fly={{ y: 200, duration: 350, delay: 250 }} >

    
    {#if view == 'brand'}
    <div class="section" style="min-height:100vh;" id="brand-grid" >
        <div class="aos" id="a">
            <ProjectNew
                link="/asucd"
                img="img/asucd/asucd-hero-image-2.svg"
                projecttitle="ASUCD"
                projecthook="Building a <span class='underline'>unified brand system</span> for UC Davis's largest student organization."
                role1="creative direction"
                category='brand'    
            />
        </div>

        <div class="aos" id="b">
            <ProjectNew

                link="/mental-health-initiative"
                img="img/mhi/MHI_Tote_Mockup.avif"
                projecttitle="Mental Health Initiative"
                projectdesc="Merchandise, Social Media Campaign"
                category='brand'
                role1="creative direction"
            />
        </div>

        <div class="aos" id="c">
            <ProjectNew
                    link="/sunset-fest-24"
                    img="img/ssf24/Poster.avif"
                    addywinner='true'
                    category='brand'
                    role1="creative direction"
                    projecttitle="Sunset Fest 2024"
                    projectdesc="Integrated Advertising Campaign"
                />
        </div>

        <div class="aos" id="d">
            <ProjectNew img="img/mooseum/67f2f56286b62a2ae012baae_P1088585.avif"
                link="/mooseum"
                category="brand"
                addywinner='true'
                role1="creative direction"
                projecttitle="Moo-vin' Moo-seum"
                projecthook="Transforming student awareness of campus resources through <span class='underline'>playful, story-driven design.</span>"
            />
        </div>

        <div class="aos" id="e">
            <ProjectNew
                link="/elections"
                img="img/elections/poster.avif"
                addywinner='true'
                category='brand'
                role1='creative direction'
                role2='design'
                projecttitle="ASUCD Elections"
                projecthook="Revitalizing voter engagement with a <span class='underline'>clear, accessible</span> election <span class='underline'>marketing campaign.</span>"
            />
        </div>

        <div class="aos" id="f">
            <ProjectNew
                link="/nu-alpha-kappa"
                img="img/nak/NAK-hero.svg"
                category='brand'
                role1='design'
                projecttitle="Nu Alpha Kappa Fraternity Inc."
                projectdesc="Print & Social Media Campaigns"
            />
        </div>
        
        <div class="aos" id="g">
            <ProjectNew
                link="/la-gran-tardeada"
                img="img/la-gran-tardeada/cover.svg"
                projecttitle="La Gran Tardeada"
                projectdesc="Merchandise, Event Design"
                category='brand'
                role1='design'
            />
        </div>

        <div id="A" class="items">
            <Item
                img='img/film.png'
                text='35mm film of choice'
                alt='kodak portra 400'
            />
        </div>

        <div id="B" class="items">
            <Item
                img='img/vaseline.png'
                text='my life saver'
                alt='vaseline'
            />
        </div>

        <div id="C" class="items">
            <Item
                img='img/pistachio1.png'
                text='oops!'
                alt='pistachios'
            />
        </div>
    </div>   
    {:else if view == 'product'} 
    <div class="section" style="min-height:100vh;" id="product-grid">
        <div class="aos" id="a">
            <ProjectNew
                link="/memorial-union"
                img="img/memorial-union/header.webp"
                projecttitle="Memorial Union App"
                projecthook="Building a <span class='underline'>data-informed navigation app</span> to help students find services faster and feel more connected on campus."
                role1="figma"
                role2="case study"
                category='product'
            />
        </div>

        <div class="aos" id="b">
            <ProjectNew 
                link="/applebttm"
                img="img/applebttm/header.webp"
                projecttitle="Applebttm"
                projecthook="Reinventing <span class='underline'>music discovery</span> through community, conversation, and <span class='underline'>clean UX.</span>"
                role1='figma'
                role2='case study'
                category='product'
            />
        </div>

        <div class="aos" id="c">
            <ProjectNew
                link='https://gyfigueroa.github.io/des157b/capstone/version2/index.html'
                img="img/project-covers/gorillai.webp"
                projecttitle='The GorillAI Problem'
                projectdesc="Interactive Narrative"
                target="_blank"
                role1='html/css'
                role2='gsap'
                category='product'
            />
        </div>

        <div class="aos" id="d">
            <ProjectNew
                link='https://iandunk.github.io/ECS163-Final-Project/index.html'
                img="img/project-covers/cinema.webp"
                projecttitle='Cinema Data Stories'
                projectdesc="Interactive Dashboard"
                target="_blank"
                role1='html/css'
                role2='d3.js'
                category='product'
            />
        </div>

        <div class="aos" id="e">
            <ProjectNew
                link='https://gyfigueroa.github.io/des157a/studio2/index.html'
                img="img/project-covers/everypicture.webp"
                projecttitle='Film Journal'
                projectdesc="Interactive Web Gallery"
                target="_blank"
                role1='html/css'
                role2=".js"
                category='product'
            />
        </div>

        <div class="aos" id="f">
            <ProjectNew
                link='https://gyfigueroa.github.io/des157a/studio3/index.html'
                img="img/project-covers/pig.webp"
                projecttitle='Game of PIG'
                projectdesc="Interactive Web Game"
                target="_blank"
                role1='html/css'
                role2=".js"
                category='product'
            />
        </div>

        <div class="aos" id="g">
            <ProjectNew
                link='https://gyfigueroa.github.io/des157a/final/project/index.html'
                img="img/project-covers/madlibs.webp"
                projecttitle='Madlibs'
                projectdesc="Interactive Web App"
                target="_blank"
                role1='html/css'
                category='product'
            />
        </div>

        <div class="items" id="A">
            <Item
                img='img/patch.png'
                text='six-one-nine'
                alt='san diego padres'
            />
        </div>

        <div class="items" id="B">
            <Item
                img='img/lelabo.png'
                text="i smell like"
                alt='le labo'
            />
        </div>

        <div class="items" id="C">
            <Item
                img='img/minolta.png'
                text="my dad's minolta (mine now)"
                alt='minolta'
            />
        </div>

        <div class="items" id="D">
            <Item
                img='img/lorde.png'
                text="praise the lorde!"
                alt='lorde'
            />
        </div>

        <div id="E" class="items">
            <Item
                img='img/pistachio2.png'
                text='sorry about that.'
                alt='pistachios'
            />
        </div>
    </div>
    {/if}

    </div>

    {/key}



</div>


</div>

<Footer/>

</div>

<style>

    .banner2{
        display: flex;
        gap: var(--spacing2);
        background-color: brown;
        width: min-content;
    }

    .banner-anchor-2{
        position: relative;
        width: 100vw;
        transform: rotate(-3deg);
        margin: -50px;
        z-index: 5;
    }

    .banner-container{
        overflow-x: clip;
    }

    

    /* NEW GRID */

    .button-wrapper{
        padding-top: 50px;
        margin: auto;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    .button-container {
        position: relative;
        padding: 15px;
        cursor: pointer;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
    }

    #brand-button{
        transform: rotate(-5deg);
    }

    #product-button{
        transform: rotate(3deg);
    }

    .tag-button{
        font-family: var(--ffmono);
        line-height: 1em;
        font-weight: 500;
        font-size: 1.4rem; 
        padding: 0.1em 0.5em;
        background-color: gray;
        border: 2px solid lightgray;
        border-radius: 0.25em 0.25em 0.1em 0.1em;
        transition: box-shadow 0.25s, transform 0.5s;
    }

    

    #brand-button .tag-button{
        text-transform: capitalize;
        background: linear-gradient(222deg, #E0399A, #BA0D69); 
        box-shadow: inset 0px -3px 0px #E0399A, 0px 0px 0px var(--forestgreen50), 0px 0px 0px 5px var(--forestgreen20);
        border: 1px solid #b12677;
        color: #FFDAFD;
    
    }

    #product-button .tag-button{
        text-transform: capitalize;
        background: linear-gradient(222deg, #39bee0, #0dbaba); 
        box-shadow: inset 0px -3px 0px #39bee0, 0px 0px 0px var(--forestgreen50), 0px 0px 0px 5px var(--forestgreen20);
        border: 1px solid #26a8b1;
        color: #dafffe;
    }

    /* Hide the browser's default radio button */
    .button-container input {
        position: absolute;
        opacity: 0;
        cursor: pointer;
    }
    /* ON HOVER SHOW INDICATOR*/
    /* On mouse-over, add a grey background color */
    .button-container:hover input ~ .checkmark {
        background-color: var(--forestgreen5);
        cursor: url('/img/link-cursor.svg'), auto;
    }

    /* BUTTON IS SELECTED ADD INDICATOR*/
    /* When the radio button is checked, add a blue background */
    .button-container input:checked ~ .checkmark {
        background-color: var(--forestgreen20);
        cursor: url('/img/link-cursor.svg'), auto;
    }

    /* grow before click */
    #brand-button:hover input ~ .tag-button {
        box-shadow: inset 0px -3px 0px #E0399A, 0px 0px 0px var(--forestgreen50), 0px 0px 0px 7px var(--forestgreen20);
    }
    /* grow before click */
    #product-button:hover input ~ .tag-button {
        box-shadow: inset 0px -3px 0px #39bee0, 0px 0px 0px var(--forestgreen50), 0px 0px 0px 7px var(--forestgreen20);
    }


    /* BRAND SHADOW WHEN BUTTON IS SELECTED */
    /* When the radio button is checked, add a gray background */
    #brand-button input:checked ~ .tag-button {
        box-shadow: inset 0px -3px 0px #E0399A, 1px 10px 20px var(--forestgreen50), 0px 10px 0px 0.75em var(--forestgreen5);
        transform: translateY(-10px) scale(1.1);
    }

    /* PRODUCT SHADOW WHEN BUTTON IS SELECTED */
    /* When the radio button is checked, add a gray background */
    #product-button input:checked ~ .tag-button {
        box-shadow: inset 0px -3px 0px #39bee0, 1px 10px 20px var(--forestgreen50), 0px 10px 0px 0.75em var(--forestgreen5);
        transform: translateY(-10px) scale(1.1);
    }

    /* Create the indicator (the dot/circle - hidden when not checked) */
    .checkmark:after {
        content: "";
        position: absolute;
        display: none;
    }

    /* Create a custom radio button */
    .checkmark {
        position: relative;
        top: 0;
        left: 0;
        height: 5px;
        width: 5px;
        background-color: transparent;
        border-radius: 50%;
        transition: background-color 0.5s;
    }

    @media (min-width: 500px) {
        .tag-button{
            font-size: 2rem;
        }
        .button-container {
            gap: 10px;
            padding:30px;
        }

        .checkmark{
            height: 10px;
            width: 10px;
        }
    }

    #brand-grid{
        display: grid;
        grid-template-areas: 
            "a a a a a a a a"
            "a a a a a a a a"
            "a a a a a a a a"
            "a a a a a a a a"
            "a a a a a a a a"
            ". . . b b b b b"
            "A A A b b b b b"
            "A A A b b b b b"
            "A A A b b b b b"
            ". . . b b b b b"
            ". c c c c c c c "
            ". c c c c c c c "
            ". c c c c c c c "
            ". c c c c c c c "
            "d d d d d d d d"
            "d d d d d d d d"
            "d d d d d d d d"
            "d d d d d d d d"
            "d d d d d d d d"
            "d d d d d d d d"
            ". e e e e e e e"
            ". e e e e e e e"
            ". e e e e e e e"
            ". e e e e e e e"
            ". e e e e e e e"
            ". e e e e e e e"
            ". e e e e e e e"
            ". e e e e e e e"
            "B B B f f f f ."
            "B B B f f f f ."
            "B B B f f f f ."
            ". . . f f f f ."
            "g g g g . . . ."
            "g g g g . C C C"
            "g g g g . C C C"
            "g g g g . C C C"
        ;
        grid-template-columns: repeat(8,1fr);
        grid-template-rows: repeat(36,1fr);
        gap: 20px;
        padding: 20px;
    }

    #product-grid{
        display: grid;
        grid-template-areas: 
            "a a a a a a a a"
            "a a a a a a a a"
            "a a a a a a a a"
            "A A A c c c c c"
            "A A A c c c c c"
            "b b b b b b b b "
            "b b b b b b b b "
            "b b b b b b b b "
            ". d d d d d . ."
            ". d d d d d . ."
            "E E . e e e e e"
            "E E . e e e e e"
            "C C C C C C C C"
            "C C C C C C C C"
            'f f f f D D D D'
            'f f f f D D D D'
            'g g g g . B B B'
            'g g g g . B B B'
        ;
        grid-template-columns: repeat(8,1fr);
        grid-template-rows: repeat(18,1fr);
        gap: 20px;
        padding: 20px;
    }

    

    @media (min-width: 1000px) {
        #brand-grid{
            grid-template-areas:
            ". a a a a a a . . . . . . . ."
            ". a a a a a a . . . . . . . ."
            ". a a a a a a . b b b . . . ."
            ". a a a a a a . b b b . A A A"
            ". a a a a a a . b b b . A A A"
            ". a a a a a a . b b b . A A A"
            ". . . . c c c c b b b . A A A"
            ". . . . c c c c b b b . . . ."
            ". B B B c c c c d d d d d d d"
            ". B B B c c c c d d d d d d d"
            ". B B B . . . . d d d d d d d"
            ". B B B . . . . d d d d d d d"
            ". . . . . . . . d d d d d d d"
            ". e e e e e . . d d d d d d d"
            ". e e e e e . . d d d d d d d"
            ". e e e e e . . . . . f f f ."
            ". e e e e e C C C C C f f f ."
            ". e e e e e C C C C C f f f ."
            ". e e e e e C C C C C f f f ."
            ". e e e e e C C C C C f f f ."
            ". e e e e e g g g . . . . . ."
            ". e e e e e g g g . . . . . ."
            ". e e e e e g g g . . . . . ."
            ". . . . . . g g g . . . . . ."
            ". . . . . . g g g . . . . . ."
            ;
            grid-template-columns: repeat(15,1fr);
        grid-template-rows: repeat(24,0.5fr);
        }
    

        #product-grid{
            grid-template-areas:
            ". a a a a a a . . . . . . . ."
            ". a a a a a a . b b b b b b b"
            ". a a a a a a . b b b b b b b"
            ". a a a a a a . b b b b b b b"
            "B B B B c c c c b b b b b b b"
            "B B B B c c c c b b b b b b b"
            "B B B B c c c c A A A A A A A"
            "B B B B c c c c A A A A A A A"
            "d d d d d D D D D D C C C C C"
            "d d d d d D D D D D C C C C C"
            "d d d d d D D D D D C C C C C"
            "d d d d d D D D D D C C C C C"
            ". e e e e D D D D D f f f . ."
            ". e e e e E E E . . g g g . ."
            ". . . . . . . . . . . . . . ."
            ;
            grid-template-columns: repeat(15,1fr);
        grid-template-rows: repeat(13,0.25fr);
        }
    }

    

    #a{
        grid-area: a;
    }

    #b{
        grid-area: b;
    }

    #c{
        grid-area: c;
    }

    #d{
        grid-area: d;
    }

    #e{
        grid-area: e;
    }

    #f{
        grid-area: f;
    }

    #g{
        grid-area: g;
    }

    #A{
        grid-area: A;
    }

    #B{
        grid-area: B;
    }

    #C{
        grid-area: C;
    }

    #D{
        grid-area: D;
    }

    #E{
        grid-area: E;
    }

    .items{
        display: flex;
        align-items: center;
        justify-content: center;
        
    }


    /* NEW GRID */



    .landing{
        width: 100vw;
        height: calc(100vh + 100px);
        /* background-color: #1F5526; */
        background-image: url(/img/glass.gif);
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
        backdrop-filter:  blur(5px) saturate(2.5);
        z-index: 1;
    }

    .right-col{
        padding: var(--spacing5);
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        background-color: var(--forestgreen50);
        backdrop-filter:  blur(5px) saturate(2.5);
        box-shadow: 0px 0px 0px 1px var(--smoke50), inset 0px 0px 20px var(--forestgreen50);
    }

    .gallery-container{
        min-height: 100vh;
    }


    @media screen and (min-width: 600px) {
    /* CSS rules to apply when the screen width is 600px or less */
        .landing {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: auto;
        }

    }

    @media screen and (min-width: 800px) {
    /* CSS rules to apply when the screen width is 600px or less */
        .landing {
            grid-template-columns: 1fr 1fr;
            grid-template-rows: auto;
        }

    }


    .banner-element {
        color: orange;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 6rem;

        /* font-size: 40pt;
        font-family: "Yesteryear", cursive; */
    }

    


</style>





