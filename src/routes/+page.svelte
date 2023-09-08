<script>
        import Newsletter from "./Newsletter.svelte";
</script>

<div class="container">
        <div class="meme">
                <p>
                        Lorem ipsum dolor, sit amet consectetur adipisicing
                        elit. Nesciunt, odio. Optio ea fuga architecto, labore,
                        omnis quidem nemo provident ipsum corrupti doloribus
                        sint? Iste ad culpa, alias explicabo ut laborum.
                </p>
        </div>
        <Newsletter />
</div>

<style>
        .container {
                display: grid;
                grid-template-rows: 800px auto;
                background: salmon;
                color: white;
                font-family: "CircularSpotifyText", -apple-system,
                        BlinkMacSystemFont, sans-serif;
        }
        .meme {
                display: grid;
                justify-content: center;
                align-content: center;
        }
        p {
                font-size: 40px;
                font-weight: 600;
                text-align: center;
        }
</style>
