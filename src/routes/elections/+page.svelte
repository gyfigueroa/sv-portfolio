<script>
    
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>
<svelte:head>
    <title>ASUCD Elections • Gabriel Figueroa Design</title>
</svelte:head>

<Header/>
<Hero
    category="Integrated Advertising Campaign"
    title="ASUCD Elections"
    role="Project Managers"
    names="Alexander Motawi, Gabriel Figueroa"
    role2='Lead Designers'
    names2='Gabriel Figueroa, Judy Yang, Joyce Pau, Joanne Sun'
    role3='Design Team'
    names3='Nicole Paja, Sara Galvis, Emilee Lu'
    role4='Social Media'
    names4='Amy Gonzalez'
    text="ASUCD student government elections had historically struggled with low voter turnout, prompting a need to reimagine how the elections connected with students. For the Spring 2024 cycle, I co-led creative direction and design ideation, introducing a playful visual identity built around friendly, bouncy 3D forms to replace the previous disjointed system."
    text2="The flexible design language scaled seamlessly into the Fall 2024 cycle, creating a cohesive and recognizable presence across multiple election periods. The refreshed identity contributed to a 10% increase in voter turnout, with 24% of the student population participating — a meaningful and rewarding shift in civic engagement on campus."
    img="img/elections/Stickers.avif"
/>

<div class="grid-bg" style="background-color: #041624;">

<section>
    <div class="gallery">
        <img src="img/elections/Spring-TableTent.avif" alt="" class="gallery-img">
        <img src="img/elections/Fall-TableTent.avif" alt="" class="gallery-img">
        <img src="img/elections/Coupons.avif" alt="" class="gallery-img">
        <img src="img/elections/Spring-IGStories.avif" alt="" class="gallery-img">
        <img src="img/elections/IGPosts.avif" alt="" class="gallery-img">
        <img src="img/elections/Fall-VoterGuide2.avif" alt="" class="gallery-img">
    </div>
</section>

<Footer/>

</div>

<style>

.gallery{
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    grid-template-areas:
    "A A A A B B"
    "C C C C C C"
    "D D D D . ."
    ". . . E E E"
    "F F F F F F";
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
</style>