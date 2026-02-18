<script>
    export let img;
    export let alt='';
    export let text='';
</script>

<div class="container">
    <div class="wrapper">
        <img src="{img}" alt="{alt}">
        <p class="text mono">{text}</p>
    </div>
</div>

<style>
    .container{
        padding: 10px;  
        
        border: transparent;

        transition: all 0.5s ease;
    }

    .wrapper{
        padding: 0px;

        background-color: transparent;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        gap: var(--spacing2);

        transition: all 0.5s ease;
    }

    img{
        margin: auto;
        /* height: auto; */
        aspect-ratio: auto;
        max-width: fit-content;
        max-height: fit-content;
        filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.5));

        transition: all 0.5s ease;
    }

    @keyframes wiggle{
        0%{ transform: scale(1) translateY(0px) rotate(0deg)}
        30%{transform: scale(1.1) translateY(-10px) rotate(-8deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        43.3%{transform: scale(1.1) translateY(-10px) rotate(9deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        56.6%{transform: scale(1.1) translateY(-10px) rotate(-5deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        70%{transform: scale(1.1) translateY(-10px) rotate(6deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        100%{ transform: scale(1) translateY(0px) rotate(0deg)}
    }

    @keyframes wiggle-noscale{
        0%{ transform: scale(1) translateY(0px) rotate(0deg)}
        30%{transform: scale(1) translateY(-10px) rotate(-8deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        43.3%{transform: scale(1) translateY(-10px) rotate(9deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        56.6%{transform: scale(1) translateY(-10px) rotate(-5deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        70%{transform: scale(1) translateY(-10px) rotate(6deg); filter: drop-shadow(0px 10px 10px rgba(0, 0, 0, 0.5));}
        100%{ transform: scale(1) translateY(0px) rotate(0deg)}
    }

    /* img:hover{
        animation: 1s wiggle alternate ease-in-out ;
    } */

    p{
        
        text-align: center;
        color: var(--forestgreen50);
        opacity: 0;

        transition: all 0.5s ease;
    }

    

    .wrapper:hover img {
        animation: 1s wiggle alternate ease-in-out ;
    }

    

    @media (min-width: 600px) {
        .wrapper{
            padding: 40px;
        }

        .wrapper:hover{
            background-color: var(--forestgreen5);
        }

        .wrapper:hover > p {
            opacity: 100;
        }
        .container:hover{
            border-image: url("/img/itemcorners.svg") 35 / auto ;
        }

    }


    
</style>