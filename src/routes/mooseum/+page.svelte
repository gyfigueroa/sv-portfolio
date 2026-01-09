<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
    import Link from "../../components/Link.svelte";
</script>

<svelte:head>
    <title>Moo-vin' Moo-seum' • Gabriel Figueroa Design</title>
</svelte:head>


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
    text="The Moovin’ Mooseum is a public art initiative created by Aggie Arts and Unitrans to promote sustainability, community connection, and student creativity. Instead of traditional interior advertisements, the program transformed bus interiors into rotating galleries featuring artwork from local artists and students."
    text2="I led the creative direction for a full exterior bus wrap designed to stand out within Unitrans’ fleet while celebrating the Davis community and highlighting ASUCD’s role in connecting campus resources. The playful, sticker-like graphics are linked by a dotted line — a visual nod to ASUCD’s motto, “Connecting the dots” — resulting in a highly recognizable, mobile installation experienced daily by thousands of riders."
    img="img/mooseum/67f2f56286b62a2ae012baae_P1088585.avif"
    link='https://theaggie.org/2024/11/01/unitrans-unveils-asucds-new-moo-vin-moo-seum/'
    linktext='Featured in The California Aggie'
/>

    
<div class="grid-bg">

<section>
    <div class="gallery">
        <img src="img/mooseum/67f2f99110db00cd6a8696c8_P1088636.avif" alt="" class="gallery-img">

        <img src="img/mooseum/67f2f990bac782558b866ec9_P1088632.avif" alt="" class="gallery-img">
        
        <img src="img/mooseum/67f2f9916b03453b3a49a3c8_P1088607.avif" alt="" class="gallery-img">
    </div>
</section>

<Footer/>

</div>


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


