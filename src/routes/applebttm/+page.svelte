<script>
    import Hero from "../../components/Hero.svelte";
    import Header from "../../components/Header.svelte";
    import Footer from "../../components/Footer.svelte";
    import Link from "../../components/Link.svelte";
</script>

<Header/>

<Hero
    category="UI/UX Case Study"
    title="Applebttm"
    role="DES 112"
    names='Gabriel Figueroa'
    text="Applebttm is a music review and discovery platform inspired by Goodreads and Letterboxd, designed to let users share opinions, rate albums, and uncover new artists. Built around intuitive navigation and streamlined onboarding, the app balances social engagement with simplicity to reduce cognitive overload."
    img="img/applebttm/header.webp"
/>

<section>
    <div class="article-grid margin3">
        <div id="a">
            <h1>Overview</h1>
            <p>Applebttm is a music review and discovery platform designed to fill a gap in the digital landscape: while Goodreads (books) and Letterboxd (films) exist, there has been no equivalent for music. Applebttm enables users to rate albums, write reviews, make lists, and discover new artists through a socially engaging, intuitive interface. This project was developed as a project for DES 112 at UC Davis, where I led UX research, prototyping, and usability testing.</p>
        </div>

        <div class="slider" id="a2">
            <img src="img/applebttm/mockup1.webp" alt="" class="img-border " >
        </div>

        <div id="b">
            <h1>The Problem</h1>
            <p>Despite music being a central part of culture, there is no dedicated platform where users can review albums and share opinions in the same way readers and film fans do. Existing review apps for other media often overwhelm users with cluttered feeds, frontloaded onboarding, or poorly designed activity tabs. The challenge was to create a platform that preserves the social joy of discovery while reducing cognitive overload.</p>
        </div>

        <div id="c">
            <h1>Research & Insights</h1>
            <p>I began by analyzing the strengths and weaknesses of apps like Goodreads and Letterboxd. Focus groups revealed that users appreciated the social aspects (ranking, reviews, activity feeds), but disliked being shown every action from friends and wanted smarter ways to discover new content.</p>
            <h2>Key Insights</h2>
            <div class='emphasis-container'>
                <div class='item'>
                    <p class="label">Strengths</p>
                    <p>Social ranking, list-making, community interaction.</p>
                </div>
                <div class='item'>
                    <p class="label">Weakness</p>
                    <p>Overload of information, confusing navigation, limited personalization.</p>
                </div>
                <div class='item'>
                    <p class="label">Opportunities</p>
                    <p>Spotlight rising artists, enable curated feeds, design for shareable moments.</p>
                </div>
                <div class='item'>
                    <p class="label">Threats</p>
                    <p>Risk of being too similar to competitors or devolving into spam.</p>
                </div>
            </div>
            <p>These insights shaped the foundation of Applebttm.</p>
        </div>

        <div id="d">
            <h1>Design Goals</h1>
            <ul>
                <li>Reduce onboarding friction and cognitive overload.</li>
                <li>Provide intuitive navigation through clear iconography and simple flows.</li>
                <li>Spotlight new and upcoming artists to encourage music discovery.</li>
            </ul>
        </div>

        <div id="e">
            <h1>The Solution</h1>
            <p>The final prototype is structured around four core tabs:</p>
            <ol>
                <li><b>Profile</b>: Users see all their reviews chronologically and access their lists.</li>
                <li><b>Create</b>: A simple flow for rating albums and posting reviews.</li>
                <li><b>Activity</b>: A curated feed of friends’ activity designed to reduce clutter.</li>
                <li><b>Discover</b>: A hub highlighting trending albums, top reviews, and up-and-coming artists.</li>
            </ol>
            <p>These design choices emphasized clarity and usability while keeping the social discovery aspect fun.</p>
            
        </div>

        <div class="slider" id="b2">
            <img src="img/applebttm/mockup2.webp" alt="" class="img-border " >
        </div>

        <div id="f">
            <h1>Usability Testing</h1>
            <p>I conducted usability tests with five participants including a mix of peers and non-designers. Key findings included:</p>
            <div class="emphasis-container">
                <div class="item">
                    <p class="label">Onboarding</p>
                    <p>Users wanted more control → added back/skip options.</p>
                </div>
                <div class="item">
                    <p class="label">Activity Feed</p>
                    <p>Lightning-bolt nav bar icon was unclear and the feed was overwhelming → replaced icon, simplified layout, increased text legibility.</p>
                </div>
                <div class="item">
                    <p class="label">Rating Albums</p>
                    <p>Users weren’t sure how to start reviews → clarified icons, added text input, improved flow.</p>
                </div>
            </div>
            <p>These refinements made the app more approachable and user-friendly.</p>
        </div>

        <div id="g">
            <h1>Impact & Takeaways</h1>
            <p>Applebttm reinforced the importance of iterative testing—what seems obvious to a designer may be confusing to users. I learned how critical it is to balance engagement with clarity, especially in socially driven platforms. The project also gave me hands-on experience with prototyping in Figma and running usability tests that directly informed design decisions.</p>
            <Link link="#" linktext="View full prototype" transparency="no"/>
        </div>

        <div class="slider" id="c2">
            <img src="img/applebttm/header.webp" alt="" class="img-border">
        </div>
        


    </div>
</section>

<Footer/>

<style>

    
    .article-grid{
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: var(--spacing3);
        grid-template-areas:
        "A A2"
        "B A2"
        "C A2"
        "d b2"
        "e b2"
        "f b2"
        "g b2"
        "c2 c2";

    }
    @media screen and (max-width: 600px) {
        .article-grid{
            display: block;
        }
    }

    #a{
        grid-area: A;
    }

    #a2{
        grid-area: A2;
    }

    #b{
        grid-area: B;
    }

    #b2{
        grid-area: b2;
    }

    #c{
        grid-area: C;
    }

    #c2{
        grid-area: c2;
    }

    #d{
        grid-area: d;
    }

    #e{
        grid-area: e;
    }

    
</style>