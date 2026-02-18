<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<svelte:head>
    <title>Mental Health Initiative • Gabriel Figueroa Design</title>
</svelte:head>

<Header/>

<Hero
    category="MERCHANDISE, SOCIAL MEDIA CAMPAIGN"
    title="Mental Health Initiative Conference"
    role="Project Manager"
    names="Gabriel Figueroa"
    role2="Lead Designer"
    names2="Joyce Pau"
    text="The Mental Health Initiative’s 2025 conference centered on the theme “Bloom As You Are,” using the metaphor of growth — planting, budding, and blooming — to celebrate individual journeys toward well-being. I led the creative direction for a flower-forward, groovy visual identity that expressed this philosophy across all conference materials."
    text2="Deliverables included event apparel, social media graphics, signage, and a program brochure, creating a cohesive and welcoming experience for attendees throughout the day."
    img='img/mhi/mhi-hero-image-3.svg'
/>

<div class="grid-bg">

<section>
    <div class="gallery">
        <img src="img/mhi/MHI_Tshirt_Mockup_2.avif" alt="" class="gallery-img">
        <img src="img/mhi/MHI_Tote_Mockup.avif" alt="" class="gallery-img">
        <img src="img/mhi/MHI_Stickers_Mockup_2 Large.avif" alt="" class="gallery-img">
    </div>
</section>

<Footer/>

</div>

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