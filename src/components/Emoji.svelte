<script>
    export let emoji;
</script>

    <div class="emoji-container">
        <p class="emoji">{emoji}</p>
    </div>

<style>
    .emoji-container{
        width: 50px;
        height: 50px;
        background-color: green;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        background: linear-gradient(to top, var(--color1,#3acfd5) 0%, var(--color2,#3a4ed5) 100%);
        box-shadow: inset 0px 5px 5px -2px var(--color1,#3acfd5), inset 0px -5px 5px -2px var(--color2,#3a4ed5);
        position: relative;
        margin: var(--spacing2);
    }

    .emoji-container::before{
        border-radius: 50%;
        content: '';
        background-image: linear-gradient(to bottom, var(--color1,#3acfd5) 0%, var(--color2,#3a4ed5) 100%);
        padding: var(--spacing1);
        width: 100%;
        height: 100%;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        position: absolute;
        z-index: -1;
    }

    .emoji{
        font-size: 18pt;
        margin: 0;
    }
</style>
