<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<svelte:head>
    <title>Sunset Fest 2024 • Gabriel Figueroa Design</title>
</svelte:head>

<Header/>

<Hero
    category="MERCHANDISE, INTEGRATED ADVERTISING CAMPAIGN"
    title="Sunset Fest 2024"
    role="Project Manager"
    names="Gabriel Figueroa"
    role2="Lead Designer"
    names2="Joyce Pau"
    text="Sunset Fest is ASUCD’s annual homecoming music festival, welcoming the new academic year with a large-scale campus celebration. For Sunset Fest 2024, our team developed a minimal, modular visual identity within a tight one-month timeline, using warm sunset color blocks and repeating patterns designed to scale across a wide range of formats."
    text2="I served as project manager and creative lead, guiding the development of a flexible design system that supported posters, flyers, merchandise, signage, and social media assets while enabling partner teams, including Entertainment Council, to produce additional materials that remained cohesive and on-brand."
    img="img/ssf24/Poster.avif"
/>
<div class="grid-bg">

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

</div>

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
