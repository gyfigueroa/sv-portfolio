<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<Header/>

<Hero
    category="MERCHANDISE, SOCIAL MEDIA CAMPAIGN"
    title="MHI Conference"
    role="Project Manager"
    names="Gabriel Figueroa"
    role2="Lead Designer"
    names2="Joyce Pau"
    textHTML="<p>The theme for Mental Health Initiative's 2025 Mental Health Conference is “Bloom As You Are”. A flower going through many stages like being planted, budding, and blooming to reach its true self is a philosophy the Mental Health Initiative wanted to spotlight with this year's theme.</p><p>I led the creative direction for the flower-studded, groovy identity we went with for all the deliverables on this project including a T-shirt, tote bag, social media posts, and an event brochure to guide attendees through the whole day.</p>"
    img='img/mhi/mhi-hero-image-3.svg'
/>



<section>
    <div class="gallery">
        <img src="img/mhi/MHI_Tshirt_Mockup_2.avif" alt="" class="gallery-img">
        <img src="img/mhi/MHI_Tote_Mockup.avif" alt="" class="gallery-img">
        <img src="img/mhi/MHI_Stickers_Mockup_2 Large.avif" alt="" class="gallery-img">
    </div>
</section>

<Footer/>

<style>
.gallery{
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-areas:
    "A A A ."
    ". . B B"
    "C C B B"
    ". . B B";
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
</style>