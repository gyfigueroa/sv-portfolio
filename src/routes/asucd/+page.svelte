<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>
<svelte:head>
    <title>ASUCD • Gabriel Figueroa Design</title>
</svelte:head>

<Header/>

<Hero
    category="BRAND GUIDELIES, BRAND IDENTITY"
    title='Associated Students of UC Davis (ASUCD)'
    role='Project Manager'
    names='Gabriel Figueroa'
    role2="Lead Designers"
    names2="Joyce Pau, Nicole Paja"
    role3="Design Team"
    names3="Judy Yang, Joanne Sun, Sara Galvis, Emilee Lu"
    role4="Copywriters"
    names4="Daniella Campuzano, Tanika Anbuchelvan"
    img="img/asucd/asucd-hero-image.svg"
    text="ASUCD is more than student government at the University of California, Davis — it operates the campus coffee shop, bike repair store, and citywide bus system, making it the largest student-run organization in the U.S. Guided by the mantra “Building tomorrow together,” ASUCD creates opportunities that shape the daily student experience across campus."
    text2="To expand access to university resources and address long-standing inconsistencies across its many sub-organizations, I led a comprehensive brand refresh to better align ASUCD with UC Davis while unifying the visual identities of over 30 internal units, committees, and commissions."
    text3="As part of this effort, we introduced Dottie, a new mascot designed to humanize the brand and reinforce ASUCD’s “by students, for students” mission. More than a visual asset, Dottie represents an engaged student navigating ASUCD’s ecosystem — bridging the gap between institution and community through a cohesive, playful, and scalable brand system."
    linktext="View the updated brand guide"
    link="https://ucdavis.app.box.com/s/xowxwqip8wxsh4ngr6cci0ueou3x17hy"
/>



<section>
    <div class="gallery">
        <img src="img/asucd/IntroducingDottie.jpg" alt="" class="gallery-img">
        <img src="img/asucd/ValentinesCrewneckMockup.jpg" alt="" class="gallery-img">
        <img src="img/asucd/BrandColors.jpg" alt="" class="gallery-img">

        <img src="img/asucd/SecondaryColors.jpg" alt="" class="gallery-img">
        <img src="img/asucd/StPattysCrewneckMockup.jpg" alt="" class="gallery-img">
        <img src="img/asucd/bikeshirtmockup.jpg" alt="" class="gallery-img">

        <img src="img/asucd/UnitLogoUsage.jpg" alt="" class="gallery-img">
        <img src="img/asucd/AdditionalLogos.jpg" alt="" class="gallery-img">
        <img src="img/asucd/HelloProximaNova.jpg" alt="" class="gallery-img">

        <img src="img/asucd/januaryshirtmockup.jpg" alt="" class="gallery-img">
        <img src="img/asucd/ASUCD Cow Gif.gif" alt="" class="gallery-img">
        <img src="img/asucd/quarterly-showcase-shirt.jpg" alt="" class="gallery-img">

        <img src="img/asucd/Brand Assets.jpg" alt="" class="gallery-img">
        <img src="img/asucd/UnitSignatures.jpg" alt="" class="gallery-img">
        <img src="img/asucd/ASUCD_SpringEvents_TradingCards_v5_NP-01.png" alt="" id="trading-card-1">
        <img src="img/asucd/ASUCD_SpringEvents_TradingCards_v5_NP-02.png" alt="" id="trading-card-2">
        <img src="img/asucd/ASUCD_SpringEvents_TradingCards_v5_NP-04.png" alt="" id="trading-card-3">
        <img src="img/asucd/ASUCD_SpringEvents_TradingCards_v5_NP-03.png" alt="" id="trading-card-4">

        <img src="img/asucd/HoloSticker.png" alt="" class="sticker" id="holo-sticker">
        <img src="img/asucd/ASUCD_AssortedStickersKeychains_v2_NP-04-2.png" alt="" class="sticker" id="ghibli-sticker">
        <img src="img/asucd/BikeSticker.png" alt="" class="sticker" id="bike-sticker">
    </div>
</section>

<Footer/>

<style>
.gallery{
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-areas:
    "A A A A A A    . B B B B ."
    "C C C C D D    D D M M M M"
    "F F F F F .    . . . Q Q Q"
    "F F F F F E    E E E Q Q Q"
    ". . . . . E    E E E . . ."
    "G G G G H H    H H N N N N"
    "O O O . . .    I I I I I I"
    "O O O P P P    I I I I I I"
    ". . . P P P    . . R R R ."
    ". . J J J J    J J R R R ."
    ". . J J J J    J J R R R ."
    "K K K K K K    . . L L L L";
    position: relative;
    
}

.gallery-img{
    position: relative;
}

.sticker{
    position: absolute;
    height: 5%;
    width: auto;
    transition: all 0.5s;
    filter: drop-shadow(2px 2px 2px rgba(0, 0, 0, 0.5));
}

#holo-sticker{
    right: 5%;
    top: 10%;
    rotate: 20deg;
}

#ghibli-sticker{
    left: 25%;
    top: 35%;
    rotate: -5deg;
}

#bike-sticker{
    left: 10%;
    top: 70%;
    rotate: 5deg;
}

.sticker:hover{
    transform: scale(1.2) rotate(-10deg);
    filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.5));
}


.gallery-img:nth-of-type(1){
    grid-area: A;
}

.gallery-img:nth-of-type(2){
    grid-area: B;
}

.gallery-img:nth-of-type(3){
    grid-area: C;
}

.gallery-img:nth-of-type(4){
    grid-area: D;
}

.gallery-img:nth-of-type(5){
    grid-area: E;
}

.gallery-img:nth-of-type(6){
    grid-area: F;
}

.gallery-img:nth-of-type(7){
    grid-area: G;
}

.gallery-img:nth-of-type(8){
    grid-area: H;
}

.gallery-img:nth-of-type(9){
    grid-area: I;
}

.gallery-img:nth-of-type(10){
    grid-area: J;
}

.gallery-img:nth-of-type(11){
    grid-area: K;
}

.gallery-img:nth-of-type(12){
    grid-area: L;
}

.gallery-img:nth-of-type(13){
    grid-area: M;
}

.gallery-img:nth-of-type(14){
    grid-area: N;
}

#trading-card-1{
    grid-area: O;
}

#trading-card-2{
    grid-area: P;
}

#trading-card-3{
    grid-area: Q;
}
#trading-card-4{
    grid-area: R;
}

</style>