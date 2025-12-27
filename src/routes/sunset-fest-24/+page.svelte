<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<Header/>

<Hero
    category="MERCHANDISE, INTEGRATED ADVERTISING CAMPAIGN"
    title="Sunset Fest 2024"
    role="Project Manager"
    names="Gabriel Figueroa"
    role2="Lead Designer"
    names2="Joyce Pau"
    textHTML="<p>Sunset Fest is ASUCD’s annual homecoming music festival that takes place every Fall marking the start of a new school year. For Sunset Fest 2024, within a month, we brought to life a minimalistic and modular identity using warm sunset color blocks and repeating design patterns so everything could be seamlessly integrated into variously sized deliverables on a tight deadline. The full suite of assets we delivered included designs for a T-shirt, tote bag, stickers, flyers, and social media posts with additional social media assets being designed by Entertainment Council design directors.</p>"
    img="img/ssf24/Poster.avif"
/>

<section>
    <div class="gallery">
            <img src="img/ssf24/LCD-Screen.avif" alt="" class="gallery-img">
            <img src="img/ssf24/Tote-Bag.avif" alt="" class="gallery-img">
            <img src="img/ssf24/T-shirt.avif" alt="" class="gallery-img">
            <img src="img/ssf24/Flyer.avif" alt="" class="gallery-img">
            <img src="img/ssf24/Square-Stickers.avif" alt="" class="gallery-img">
            <img src="img/ssf24/Circle-Sticker-Mockup-1.avif" alt="" class="gallery-img">
            <img src="img/ssf24/SSF-Hero.avif" alt="" class="gallery-img">
    </div>
</section>

<Footer/>

<style>
.gallery{
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-areas:
    "A A A ."
    "B B C C"
    ". D D D"
    "E E F F"
    "G G G .";
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
</style>
