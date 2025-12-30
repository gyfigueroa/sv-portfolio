<script>
    import Link from "./Link.svelte";
</script>

<footer>
    <p class="hero-text">Like what you see?</p>
    <p class="hero-serif"><i>L</i>et’s con<i>n</i>ect<i>!</i></p>
    <div class="link-group">
        <Link
            name="linkedin"
        />
        <Link
            name="mail"
        />
    </div>
</footer>

<style>
    footer{
        background-color: var(--forestgreen);
        color: var(--lime100);
        width: auto;
        height: 400px;
        margin: 0 var(--spacing4);
        border-radius: var(--spacing5) var(--spacing5) 0 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .hero-text{
        margin: 0;
    }


    footer > .hero-serif{
        margin-top: -2px;
    }
</style>