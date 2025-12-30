<script>
    export let img = 'img/GabrielCropped.jpg';
    import { onMount } from "svelte";

    const outerOuterMin = -45;
    const outerOuterMax = 45;
    const outerInnerMin = -35;
    const outerInnerMax = 35;

    const usedPositions = [];
    const MIN_DISTANCE = 20;
    const SCALE_MIN = 1;
    const SCALE_MAX = 2;
    let delayFactor = 1;

    function getRandomIntInclusive(min, max) {
        min = Math.ceil(min);
        max = Math.floor(max);
        return Math.floor(Math.random() * (max - min + 1)) + min; // The maximum is inclusive and the minimum is inclusive
    }

    function getRandomDecimalFixed(min, max, decimals) {
        const randomNumber = Math.random() * (max - min) + min;
        return parseFloat(randomNumber.toFixed(decimals));
    }

    function getRandomOuterPositionPair() {
        let x, y;

        do {
            x = getRandomIntInclusive(outerOuterMin, outerOuterMax);
            y = getRandomIntInclusive(outerOuterMin, outerOuterMax);
        } while (
            x >= outerInnerMin && x <= outerInnerMax &&
            y >= outerInnerMin && y <= outerInnerMax
        );

        return { x, y };
    }

    function getRandomOuterPositionPairNonOverlapping() {
        let x, y;
        let attempts = 0;
        const MAX_ATTEMPTS = 50;

        do {
            ({ x, y } = getRandomOuterPositionPair());
            attempts++;
        } while (isTooClose(x, y) && attempts < MAX_ATTEMPTS);

        usedPositions.push({ x, y });
        return { x, y };
    }


    function isTooClose(x, y) {
        return usedPositions.some(pos => {
            const dx = pos.x - x;
            const dy = pos.y - y;
            return Math.sqrt(dx * dx + dy * dy) < MIN_DISTANCE;
        });
    }


    function randomizeValues() {
        const { x: x1, y: y1 } = getRandomOuterPositionPairNonOverlapping();
        const x2 = parseFloat((x1/getRandomDecimalFixed(SCALE_MIN, SCALE_MAX, 2)).toFixed(2));
        const y2 = parseFloat((y1/getRandomDecimalFixed(SCALE_MIN, SCALE_MAX, 2)).toFixed(2))

        
        


        const scale = getRandomDecimalFixed(SCALE_MIN, SCALE_MAX, 2);

        console.log(`OUTER: ${x1}, ${y1} INNER: ${x2}, ${y2}`);

        return { x1, y1, x2, y2, scale };
    }


    onMount(() => {
        const emojis = document.querySelectorAll(".animator");
        emojis.forEach(wrapper => {
            const { x1, y1, x2, y2, scale } = randomizeValues();

            const emoji = wrapper.firstElementChild;

            const currID = emoji.id;
            emoji.style.background = `linear-gradient(to top, var(--${currID}1,#3acfd5) 0%, var(--${currID}2, #3a4ed5) 100%)`;
            emoji.style.boxShadow = `inset 0px -3px 3px 3px var(--${currID}2, #3a4ed5), inset 0px 3px 3px 3px var(--${currID}1,#3acfd5), 0px 5px 3px -3px rgba(0,0,0,0.75)`;
            wrapper.animate(
                [
                    // keyframes
                    {transform: `translate(0%, 0%) scale(0)`, filter: `blur(10px)`},
                    {transform: `translate(${x1}%, ${y1}%)`, easing: 'ease-out'},
                    {zIndex: 2,  filter: `blur(0px)`},
                    {transform: `translate(${x2}%, ${y2}%) scale(${scale}) rotate(0deg)`, easing: 'ease-in', zIndex:2}
                ],
                {
                    duration: 4000,
                    delay: 100 * delayFactor,
                    fill: "forwards",
                    easing: "ease"
                }
            );
            delayFactor++;
        });
    });

    
    
</script>

<div class="avatar-container">
    <img class="center img-border" src="{img}" alt="">
    <div class="animator">
        <p class="emoji center" id="fire">❤️‍🔥</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="avocado">🥑</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="splat">🫟</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="boot">🥾</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="film">🎞</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="tulip">🌷</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="mac">👨‍💻</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="bulb">💡</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="mexico">🇲🇽</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="airpods">🎧</p>
    </div>
    <div class="animator">
        <p class="emoji center" id="eggs">🍳</p>
    </div>
</div>


<style>
    :root{
        --fire1: #a80900;
        --fire2: #FF8A00;

        --avocado2: #9AFF00;
        --avocado1: #1F7A3A;

        --splat2: #B84EDB;
        --splat1:  #3c0098;

        --boot2: #5BFF8E;
        --boot1: #1D6B4A;

        --film2:  #FFC857;
        --film1:  #2B1A0F;

        --tulip2:  #FF5A8A;
        --tulip1:  #8E1C3F;

        --mac2:  #5A6CFF;
        --mac1:  #0B0F2E;

        --bulb2:  #FFE44D;
        --bulb1:  #d67c00;

        --mexico2:  #59c61e;
        --mexico1:  #2F6B4F;

        --airpods2:  #FF2F92;
        --airpods1:  #4800c2;

        --eggs2: #FFF1A8;
        --eggs1: #da8500;
    }

    .avatar-container{
        width: 100%;
        height: 100%;
        position: relative;
        transition: transform var(--animationquick) ease-in-out;
    }

    .avatar-container:hover{
        transform: scale(1.1);
    }

    .avatar-container:hover > img{
        padding: 5px;
    }
    img{
        width: 50%;
        height: auto;
        aspect-ratio: 1/1;
        border-radius: 50%;
        z-index: 1;
        position: relative;
        transition: padding var(--animationquick) ease-in-out;
    }

    .center{
        margin: 0;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .emoji{
        width: 2.25em;
        height: 2.25em;
        font-size: 1rem;
        transition: font-size var(--animationquick);
        border-radius: 50%;
        place-content: center;
        justify-items: center;
        justify-content: center;
        text-align: center;
        background: linear-gradient(to top, #3acfd5 0%, #3a4ed5 100%);
        box-shadow: inset 0px -3px 3px 3px #3a4ed5, inset 0px 3px 3px 3px #3acfd5, 0px 5px 4px -2px rgba(0,0,0,0.5);
        pointer-events: auto;
    }

    .emoji:hover{
        font-size: 1.5rem;
    }

    @media screen and (min-width: 600px) {
        .emoji{
            font-size: 1.5rem;
        }
        .emoji:hover{
            font-size: 2rem;
        }
    }

    .animator{
        transform: translate(0%, 0%) rotate(180deg);
        width: 100%;
        height: 100%;
        position: absolute;
        pointer-events: none;
        z-index: -1;
    }
</style>