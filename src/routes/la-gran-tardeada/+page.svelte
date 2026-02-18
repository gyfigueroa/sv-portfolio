<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<svelte:head>
    <title>La Gran Tardeada • Gabriel Figueroa Design</title>
</svelte:head>

<Header/>

<Hero
    category="Merchandise and Graphic Design"
    title="La Gran Tardeada"
    role="Design"
    names="Gabriel Figueroa"
    text="My poster design was selected as the winning visual identity for La Gran Tardeada, an annual UC Davis celebration hosted by the Cross Cultural Center celebrating the Chicanx/Latinx community through food, music, and dance. Drawing inspiration from the hand-painted street signage of my childhood between Tijuana and San Diego, and incorporating client-requested floral motifs, I created a vibrant, culturally grounded design that honored community identity."
    text2="The final artwork was featured across digital and physical touchpoints, including posters, totes, shirts, and stickers, helping unify promotion for the event across campus and community channels."
    img='img/la-gran-tardeada/cover.svg'
/>

<div class="grid-bg" style="background-color: #131818;">

<section>
    <div class="gallery">
        <img src="img/la-gran-tardeada/LaGranTardeadaPoster.webp" alt="" class="gallery-img">
        <img src="img/la-gran-tardeada/tshirt-mockup.png" alt="" class="" width="900px" id='tshirt'>
    </div>
</section>

<Footer/>

</div>

<style>
.gallery{
    grid-template-columns: 1fr;
    grid-template-areas:
    "B"
    "A";
}


.gallery-img:nth-of-type(1){
    grid-area: A;
}

#tshirt{
    grid-area: B;
}


@media (min-width: 600px) {
    .gallery{
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
        grid-template-areas:
        "A A A B B B B";
        align-items: center;
    }
}

</style>

