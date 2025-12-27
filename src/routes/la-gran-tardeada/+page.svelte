<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>

<Header/>

<Hero
    category="Merchandise and Graphic Design"
    title="La Gran Tardeada"
    role="Design"
    names="Gabriel Figueroa"
    textHTML="<p>My poster design was selected as the winning identity for UC Davis's La Gran Tardeada, an annual tradition hosted by the Cross Cultural Center that celebrates the Chicanx/Latinx community through food, music, and dance. Drawing from the hand-painted street-sign aesthetics of my childhood between Tijuana and San Diego and incorporating client-requested floral motifs, I created a vibrant visual that honored cultural heritage and was featured across posters, totes, shirts, and stickers.</p>"
    img='img/la-gran-tardeada/cover.svg'
/>

<section>
    <div class="gallery">
        <img src="img/la-gran-tardeada/LaGranTardeadaPoster.webp" alt="" class="gallery-img">
        <img src="img/la-gran-tardeada/tshirt-mockup.png" alt="" class="gallery-img">
    </div>
</section>

<Footer/>

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

.gallery-img:nth-of-type(2){
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

