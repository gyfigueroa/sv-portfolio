<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<svelte:head>
    <title>Nu Alpha Kappa • Gabriel Figueroa Design</title>
</svelte:head>

<Header/>

<Hero
    category="Print and Social Media Campaigns"
    title="Nu Alpha Kappa Fraternity"
    role="Director of Marketing"
    names="Gabriel Figueroa"
    text="As Director of Marketing for Nu Alpha Kappa (Kappa Chapter), I led the design and strategy behind our chapter's recruitment and philanthropy communications from 2023–2024. My work spanned digital and print design, social media campaigns, and coordination with the National Board, resulting in a cohesive brand presence that elevated our chapter's visibility through polished flyers, engaging posts, and consistent visual storytelling."
    img='img/nak/NAK-hero.svg'
/>

<section>
    <div class="gallery">
        <img src="img/nak/picnakday.webp" alt="" class="gallery-img" id="item-a">

        <img src="img/nak/tshirt-1.webp" alt="" class="gallery-img" id="item-b">

        <img src="img/nak/tshirt-2.webp" alt="" class="gallery-img" id="item-c">

        <img src="img/nak/fall-rush-23-1.webp" alt="" class="gallery-img" id="item-d">

        <div class="mini-grid-slider-container gallery-img" id="item-e">
            <div class="mini-grid-slider">
                <img src="img/nak/nakostacos-1.webp" alt="" class="mini-grid-post">
                <img src="img/nak/nakostacos-2.webp" alt="" class="mini-grid-post">
            </div>
        </div>
        <div class="mini-grid-slider-container gallery-img" id="item-f">
            <div class="mini-grid-slider">
                <img src="img/nak/Slice 31.webp" alt="" class="mini-grid-post">
                <img src="img/nak/Slice 32.webp" alt="" class="mini-grid-post">
                <img src="img/nak/Slice 33.webp" alt="" class="mini-grid-post">
                <img src="img/nak/Slice 34.webp" alt="" class="mini-grid-post">
                <img src="img/nak/Slice 35.webp" alt="" class="mini-grid-post">
                
            </div>
        </div>

        

        <div class="mini-grid-slider-container gallery-img" id="item-g">
            <div class="mini-grid-slider">
                <img src="img/nak/mta-psi/Slice 1.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-psi/Slice 2.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-psi/Slice 3.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-psi/Slice 4.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-psi/Slice 5.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-psi/Slice 6.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-psi/Slice 7.png" alt="" class="mini-grid-post">
            </div>
        </div>

        <div class="mini-grid-slider-container gallery-img" id="item-h">
            <div class="mini-grid-slider">
                <img src="img/nak/mta-chi/1.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-chi/2.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-chi/3.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-chi/4.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-chi/5.png" alt="" class="mini-grid-post">
                <img src="img/nak/mta-chi/6.png" alt="" class="mini-grid-post">
            </div>
        </div>

        <img src="img/nak/fall-rush-23-2.webp" alt="" class="gallery-img" id="item-i">



        <img src="img/nak/spring-rush-24-1.webp" alt="" class="gallery-img" id="item-j">

        <img src="img/nak/spring-rush-24-2.webp" alt="" class="gallery-img" id="item-k">

        <img src="img/nak/be-the-change.webp" alt="" class="gallery-img" id="item-l">

        <img src="img/nak/NAKLand.webp" alt="" class="gallery-img" id="item-m">

        <img src="img/nak/posada-2-1.webp" alt="" class="gallery-img" id="item-n">

    </div>
</section>

<Footer/>

<style>
.gallery{
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-areas:
    "A A B B C C"
    "D D E E F F"
    "G G G H H .";

    grid-template-areas:
    "A A A A B B"
    "A A A A B B"
    "A A A A C C"
    "A A A A C C"
    "A A A A D D"
    "E E F F D D"
    "E E F F D D"
    "G G H H I I"
    "G G H H I I"
    "J J K K I I"
    "J J K K L L"
    "J J K K L L"
    "M M N N L L"
    "M M N N . ."
    "M M N N . .";
}

.gallery-img{
    border-radius: 20px;
}


#item-a{
    grid-area: A;
}

#item-b{
    grid-area: B;
}

#item-c{
    grid-area: C;
}

#item-d{
    grid-area: D;
}

#item-e{
    grid-area: E;
}

#item-f{
    grid-area: F;
}

#item-g{
    grid-area: G;
}

#item-h{
    grid-area: H;
}

#item-i{
    grid-area: I;
}

#item-j{
    grid-area: J;
}

#item-k{
    grid-area: K;
}

#item-l{
    grid-area: L;
}

#item-m{
    grid-area: M;
}

#item-n{
    grid-area: N;
}

.mini-grid-slider-container{
    display: flex;
    flex-direction: column;
    gap: var(--mini-grid-gap);
    overflow: hidden;
    position: relative;
    height: fit-content;
}

.mini-grid-slider-container::after{
    content: '';
    position: absolute;
    right: 0;
    width: 50px;
    height: 100%;
    background-color: aqua;
    background: linear-gradient(90deg,var(--sand0) 1%, var(--sand100) 90%);
}


.mini-grid-slider{
    flex: 1;
    display: flex;
    flex-direction: row;
    gap: 5px;
    position: relative;
    overflow: scroll;
    border-radius: calc( var(--spacing4) - 10px);
}


.mini-grid-post{
    width: 90%;
    border-radius: calc( var(--spacing4) - 10px);
}
</style>