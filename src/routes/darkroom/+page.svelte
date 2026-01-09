<script>
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
</script>
<svelte:head>
    <title>darkroom • Gabriel Figueroa Design</title>
</svelte:head>

<div class="grid-bg">

<Header/>

<section>
    <div class="gallery">
        <div class="col">
            <img src="img/darkroom/film1.webp" alt="">
            <img src="img/darkroom/film5.webp" alt="">

            <img src="img/darkroom/edgar1.webp" alt="">

            <img src="img/darkroom/lightroom1.webp" alt="">
            <img src="img/darkroom/lightroom2.webp" alt="">

            <img src="img/darkroom/judy1.webp" alt="">
            <img src="img/darkroom/judy6.webp" alt="">
            <img src="img/darkroom/judy15.webp" alt="">

            <img src="img/darkroom/film9.webp" alt="">
            <img src="img/darkroom/film10.webp" alt="">

            <img src="img/darkroom/wedding1.webp" alt="">
            <img src="img/darkroom/wedding2.webp" alt="">

            <img src="img/darkroom/film19.webp" alt="">

            <img src="img/darkroom/martha1.webp" alt="">
            <img src="img/darkroom/martha2.webp" alt="">
            <img src="img/darkroom/martha9.webp" alt="">

            <img src="img/darkroom/film23.webp" alt="">

            <img src="img/darkroom/nikon1.webp" alt="">
            <img src="img/darkroom/nikon6.webp" alt="">
        </div>
        <div class="col">
            <img src="img/darkroom/film2.webp" alt="">
            <img src="img/darkroom/film6.webp" alt="">

            <img src="img/darkroom/edgar2.webp" alt="">
            <img src="img/darkroom/edgar5.webp" alt="">
            
            <img src="img/darkroom/lightroom6.webp" alt="">

            <img src="img/darkroom/judy3.webp" alt="">
            <img src="img/darkroom/judy20.webp" alt="">
            <img src="img/darkroom/judy17.webp" alt="">

            <img src="img/darkroom/film11.webp" alt="">
            <img src="img/darkroom/film13.webp" alt="">

            <img src="img/darkroom/wedding3.webp" alt="">

            <img src="img/darkroom/film20.webp" alt="">

            <img src="img/darkroom/martha3.webp" alt="">
            <img src="img/darkroom/martha4.webp" alt="">
            <img src="img/darkroom/martha10.webp" alt="">

            <img src="img/darkroom/film24.webp" alt="">

            <img src="img/darkroom/nikon2.webp" alt="">
            
        </div>
        <div class="col">
            <img src="img/darkroom/film3.webp" alt="">
            <img src="img/darkroom/film7.webp" alt="">

            <img src="img/darkroom/edgar3.webp" alt="">

            <img src="img/darkroom/lightroom3.webp" alt="">
            <img src="img/darkroom/lightroom10.webp" alt="">

            <img src="img/darkroom/judy4.webp" alt="">
            <img src="img/darkroom/judy9.webp" alt="">
            <img src="img/darkroom/judy18.webp" alt="">

            <img src="img/darkroom/film15.webp" alt="">
            <img src="img/darkroom/film16.webp" alt="">

            <img src="img/darkroom/wedding4.webp" alt="">
            <img src="img/darkroom/wedding7.webp" alt="">

            <img src="img/darkroom/film21.webp" alt="">

            <img src="img/darkroom/martha5.webp" alt="">
            <img src="img/darkroom/martha6.webp" alt="">

            <img src="img/darkroom/film25.webp" alt="">

            <img src="img/darkroom/nikon3.webp" alt="">
            <img src="img/darkroom/nikon5.webp" alt="">
        </div>
        <div class="col">
            <img src="img/darkroom/film4.webp" alt="">
            <img src="img/darkroom/film8.webp" alt="">

            <img src="img/darkroom/edgar4.webp" alt="">

            <img src="img/darkroom/lightroom4.webp" alt="">
            <img src="img/darkroom/lightroom11.webp" alt="">

            <img src="img/darkroom/judy5.webp" alt="">
            <img src="img/darkroom/judy14.webp" alt="">
            <img src="img/darkroom/judy19.webp" alt="">

            <img src="img/darkroom/film17.webp" alt="">
            <img src="img/darkroom/film18.webp" alt="">

            <img src="img/darkroom/wedding5.webp" alt="">
            <img src="img/darkroom/wedding6.webp" alt="">

            <img src="img/darkroom/film22.webp" alt="">

            <img src="img/darkroom/martha7.webp" alt="">
            <img src="img/darkroom/martha8.webp" alt="">

            <img src="img/darkroom/film27.webp" alt="">

            <img src="img/darkroom/nikon4.webp" alt="">
        </div>
    </div>
</section>

<Footer/>

</div>

<style>

    .grid-bg{
        background: rgb(19 18 16);;
        background-image: url(/img/dotgrid.svg);
    background-repeat: repeat;
    }
    
    .gallery{
        grid-template-columns: 1fr 1fr;
        column-gap: var(--spacing3);
    }

    .col {
        display: flex;
        flex-direction: column;
        gap: var(--spacing3);
    }

    @media screen and (min-width: 600px) {
        .gallery{
            grid-template-columns: 1fr 1fr 1fr 1fr;
        }
    }
</style>