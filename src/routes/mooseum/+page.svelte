<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
    import Link from "../../components/Link.svelte";
</script>


<Header/>
<Hero
    category="Mass Transit"
    title="Moo-vin' Moo-seum"
    role="Project Manager"
    names="Gabriel Figueroa"
    role2='Lead Designer'
    names2="Joyce Pau"
    role3="Photography"
    names3='Aggie Studios'


    textHTML="<p>The Moovin' Mooseum is the newest public art program highlighting both Aggie Arts and Unitrans' commitment to sustainability and connecting its community. With its student-led curation team, the Mooseum swapped its interior ad carts for drawings and creations of local artists. I led the creative direction of a full exterior wrap that captured the unique Davis community and showcases the many resources ASUCD, Unitrans' parent organization, has to offer students. My team and I aimed to create a vibrant, playful twist on the classic red Unitrans bus that reflects the friendly and inviting nature of the campus community. The logos and icons “sticker-ed” onto the bus are connected by a dotted line mirroring ASUCD's motto: “Connecting the dots”.</p>
    <p>Featured in </p><Link link='#' linktext='The Calfornia Aggie'/>"
    img="img/mooseum/67f2f56286b62a2ae012baae_P1088585.avif"
    link='#'
    linktext='Featured in The California Aggie'
/>



<section>
    <div class="gallery">
        <img src="img/mooseum/67f2f99110db00cd6a8696c8_P1088636.avif" alt="" class="gallery-img">

        <img src="img/mooseum/67f2f990bac782558b866ec9_P1088632.avif" alt="" class="gallery-img">
        
        <img src="img/mooseum/67f2f9916b03453b3a49a3c8_P1088607.avif" alt="" class="gallery-img">
    </div>
</section>

<Footer/>



<style>
    .gallery{
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-template-areas:
        "A A A A"
        ". B B B"
        "C C C .";
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


