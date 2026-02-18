<script>
    import Project2 from "../../components/Project2.svelte";
    import ProjectNew from "../../components/ProjectNew.svelte";
    import Item from "../../components/Item.svelte";

    import { onMount } from "svelte";
    import { gsap } from 'gsap/dist/gsap';
    // For plugins, e.g., ScrollTrigger
    import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

    if (typeof window !== "undefined") {
        gsap.registerPlugin(ScrollTrigger);
    }

    let context;

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


    return () => ctx.revert(); // <- Cleanup!
  });
    
</script>

<div class="grid-bg" style="min-height: 100vh;" bind:this={context}>
    <p  class="label" style="margin: auto;">viewing {view}</p>
    <div class="section button-wrapper">
        
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

    <div class="section" style="border: 1px solid red; min-height:100vh;" id="product-grid">
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
                text='a little something from home'
                alt='san diego padres'
            />
        </div>

        <div class="items" id="B">
            <Item
                img='img/lelabo.png'
                text="how i'm smelling now"
                alt='le labo'
            />
        </div>

        <div class="items" id="C">
            <Item
                img='img/minolta.png'
                text="my dad's minolta (mine)"
                alt='minolta'
            />
        </div>

        <div class="items" id="D">
            <Item
                img='img/lorde.png'
                text="my favorite artist"
                alt='lorde'
            />
        </div>

        <div id="E" class="items">
            <Item
                img='img/pistachio2.png'
                text='excuse the mess'
                alt='pistachios'
            />
        </div>
    </div>


    <div class="section" style="border: 1px solid red; min-height:100vh;" id="brand-grid" >
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
                text='excuse the mess'
                alt='pistachios'
            />
        </div>
    </div>
        

        
        <div class="section freeform-gallery">
            <img src="/img/patch.png" alt="" class="inv-item" id="patch">
            <img src="/img/minolta.png" alt="" class="inv-item" id="minolta">
            <img src="/img/pistachio1.png" alt="" class="inv-item" id="pistachio1">
            <img src="/img/pistachio2.png" alt="" class="inv-item" id="pistachio2">
            <img src="/img/pistachio3.png" alt="" class="inv-item" id="pistachio3">
            <img src="/img/lelabo.png" alt="" class="inv-item" id="lelabo">
            <img src="/img/journal.png" alt="" class="inv-item" id="journal">
            <img src="/img/cinema.png" alt="" class="img-border2" id="cinema">
            <img src="/img/pencil.png" alt="" class="img-border2" id="pencil">
            <img src="/img/lorde.png" alt="" class="img-border2" id="lorde">
            
            
            
            <div class="freeform" id="asucd">
                <Project2
                    link="/asucd"
                    img="img/asucd/asucd-hero-image.svg"
                    projecttitle="ASUCD"
                    projecthook="Building a <span class='underline'>unified brand system</span> for UC Davis's largest student organization."
                />
            </div>

            <div class="freeform" id="mhi">
                <Project2
                    link="/mental-health-initiative"
                    img="img/mhi/mhi-hero-image-3.svg"
                    projecttitle="Mental Health Initiative"
                    projectdesc="Creative Direction • Merchandise, Social Media Campaign"
                />
            </div>

            <div class="freeform" id="ssf">
                <Project2
                    link="/sunset-fest-24"
                    img="img/ssf24/Poster.avif"
                    awardtext='ADDY® Winner'
                    projecttitle="Sunset Fest 2024"
                    projectdesc="Creative Direction • Integrated Advertising Campaign"
                />
            </div>

            <div class="freeform" id="mooseum">
                <Project2
                    link="/mooseum"
                    img="img/mooseum/67f2f56286b62a2ae012baae_P1088585.avif"
                    awardtext='ADDY® Winner'
                    projecttitle="Moo-vin' Moo-seum"
                    projecthook="Transforming student awareness of campus resources through <span class='underline'>playful, story-driven design.</span>"
                />
            </div>

            

            <div class="freeform" id="elections">
                <Project2
                    link="/elections"
                    img="img/elections/poster.avif"
                    awardtext='ADDY® Winner'
                    projecttitle="ASUCD Elections"
                    projecthook="Revitalizing voter engagement with a <span class='underline'>clear, accessible</span> election <span class='underline'>marketing campaign.</span>"
                />
            </div>

            <div class="freeform" id="nak">
                <Project2
                    link="/nu-alpha-kappa"
                    img="img/nak/NAK-hero.svg"
                    projecttitle="Nu Alpha Kappa Fraternity Inc."
                    projectdesc="Design • Print & Social Media Campaigns"
                />
            </div>

            <div class="freeform" id="lgt">
                <Project2
                    link="/la-gran-tardeada"
                    img="img/la-gran-tardeada/cover.svg"
                    projecttitle="La Gran Tardeada"
                    projectdesc="Design • Merchandise, Event Design"
                />
            </div>
 
            
        </div>

        
</div>

<style>

    .button-wrapper{
        padding: 20px;
        gap: 10px;
        margin: auto;
        display: flex;
        justify-content: center;
    }
    .button-container {
        position: relative;
        padding: 35px;
        cursor: pointer;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
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
        font-size: 2rem;
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
        background-color: var(--forestgreen20);
    }

    /* BUTTON IS SELECTED ADD INDICATOR*/
    /* When the radio button is checked, add a blue background */
    .button-container input:checked ~ .checkmark {
        background-color: var(--forestgreen20);
    }

    /* BRAND SHADOW WHEN BUTTON IS SELECTED */
    /* When the radio button is checked, add a gray background */
    #brand-button input:checked ~ .tag-button {
        box-shadow: inset 0px -3px 0px #E0399A, 1px 10px 20px var(--forestgreen50), 0px 10px 0px 1em var(--forestgreen5);
        transform: translateY(-10px) scale(1.1);
    }

    /* PRODUCT SHADOW WHEN BUTTON IS SELECTED */
    /* When the radio button is checked, add a gray background */
    #product-button input:checked ~ .tag-button {
        box-shadow: inset 0px -3px 0px #39bee0, 1px 10px 20px var(--forestgreen50), 0px 10px 0px 1em var(--forestgreen5);
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
        height: 10px;
        width: 10px;
        background-color: transparent;
        border-radius: 50%;
        transition: background 0.5s;
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
        background: var(--smoke);
        background-image: url(/img/Grid2.svg);
        background-repeat: repeat;
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
        background: var(--smoke);
        background-image: url(/img/Grid2.svg);
        background-repeat: repeat;
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


    :root{
        --center-align-left: translate(-50%, 0%);
        --center-align-right: translate(50%, 0%);
    }
    .img-border2{
        border-radius: 0px;
        border-image: url("/img/border.svg") 21 / 10px / 9px round;
        position: absolute;
        height: 200px;
        width: auto;
    }

    .freeform-gallery{
        position: relative;
        text-align: center;
        display: flex;
        flex-direction: column;
        overflow-x: hidden;
    }

    .items{
        display: flex;
        align-items: center;
        justify-content: center;
        
    }

    .freeform{
        position: relative;
        /* transform: translate(-50%, -50%); */
    }

    
    #asucd{
        top: 0%;
        left: 0;
    }

    #mhi{
        align-self: flex-end;
    }

    #ssf{
        align-self: flex-start;
    }

    #mooseum{
    
    }

    #elections{

    }

    #nak{
        align-self: flex-start;
    }

    #lgt{
        align-self: flex-end;
    } 

    .inv-item{
        position: absolute;
        width: auto;
        filter: drop-shadow(0px 2px 1px);
    }

    #patch{
        left: 0%;
        top: 10%;
        transform: var(--center-align-left) rotate(30deg);
    }

    #minolta{
        top: 60%;
        /* left: 70%; */
        right: -50%;
        transform: translate(50%, 0%) /* rotate(-30deg) */;
    }

    #pistachio1{
        top: 30%;
        left: 80%;
    }

    #pistachio2{
        top: 90%;
        left: 10%;
        z-index: 4;
    }

    #lelabo{
        top: 85%;
        /* transform: rotate(15deg); */
        right: 90%;
    }


    #pistachio3, #journal, #cinema, #lorde, #pencil{
        visibility: hidden;
    }

    @media screen and (min-width: 600px) {
        .section{
            margin: auto;
            overflow: visible;
        }

        .freeform-gallery{
            min-height: 2000px;
            max-width: 1100px;
        }

        .freeform{
            position: absolute;
            
        }

        #pistachio3, #journal, #cinema, #lorde, #pencil{
            visibility: visible;
        }


        #asucd {
            top: 0%;
            left: 5%;
        }

        #mhi {
            top: 10%;
            right: 5%;
            z-index: 2;

        }

        #ssf{
            top: 20%;
            left: 10%;
        }

        #mooseum{
            top: 35%;
            right: 0%;
        }

        #elections{
            top: 55%;
            left: 2%;
        }

        #nak{
            top: 65%;
            right: 10%;
        }

        #lgt{
            top: 80%;
            left: 20%;
        } 

        #patch{
            /* left: -20%; */
        }

        #minolta{
            top: 80%;
            right: 0%;
            transform: var(--center-align-right);
        }

        #lelabo{
            top: 8%;
            right: 0%;
            transform: var(--center-align-right);
        }

        #journal{
            top: 65%;
            left: -10%;
            transform: var(--center-align-left);
            visibility: visible;
        }

        #pistachio1{
            top: 15%;
            left: 20%;
        }

        #pistachio3{
            visibility: visible;
            top: 46%;
            right: -5%;
        }

        #cinema{
            top: 40%;
            left: -5%;
            transform: var(--center-align-left);
        }

        #lorde{
            top: 50%;
            right: 0%;
            transform: var(--center-align-right);
        }

        #pencil{
            top: 57%;
            right: -7%;
            transform: var(--center-align-right);
        }

    }
</style>

