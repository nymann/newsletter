<script>
        import { draw } from "svelte/transition";
        import { quintOut } from "svelte/easing";
        import { onMount } from "svelte";
        let isVisible = false;
        let targetDiv;

        const observerOptions = {
                root: null,
                rootMargin: "0px",
                threshold: 0.7,
        };

        const handleIntersection = (entries, observer) => {
                entries.forEach((entry) => {
                        isVisible = entry.isIntersecting;
                });
        };
        onMount(() => {
                isVisible = true;
                const observer = new IntersectionObserver(
                        handleIntersection,
                        observerOptions
                );
                observer.observe(targetDiv);
        });
</script>

<div class="container" bind:this={targetDiv}>
        <p class="cta">
                Want Spotify Design updates
                <br />
                sent straight to your
                <span>
                        <span class="stroke"
                                ><svg
                                        class="swirl"
                                        xmlns="http://www.w3.org/2000/svg"
                                        viewBox="0 0 120 68"
                                        ><g
                                                fill="none"
                                                stroke="yellow"
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                        >
                                                {#if isVisible}
                                                        <path
                                                                in:draw={{
                                                                        duration: 1000,
                                                                        easing: quintOut,
                                                                }}
                                                                d="M105 10C28-9-29 40 34 56c62 16 91-29 66-29"
                                                        /><path
                                                                in:draw={{
                                                                        delay: 300,
                                                                        duration: 1000,
                                                                        easing: quintOut,
                                                                }}
                                                                d="M109 16C82-20-56 21 30 55s105-27 75-45"
                                                        />
                                                {/if}
                                        </g></svg
                                >
                                <svg
                                        class="arrow"
                                        xmlns="http://www.w3.org/2000/svg"
                                        viewBox="0 0 196 48"
                                        ><g
                                                fill="none"
                                                stroke="currentColor"
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="1.4"
                                        >
                                                {#if isVisible}
                                                        <path
                                                                in:draw={{
                                                                        duration: 1000,
                                                                        delay: 1500,
                                                                        easing: quintOut,
                                                                }}
                                                                d="M154 21c6-2 13-4 23 0-13-5-16-8-18-15"
                                                        /><path
                                                                in:draw={{
                                                                        delay: 500,
                                                                        duration: 1000,
                                                                        easing: quintOut,
                                                                }}
                                                                d="M14 28c29-22 101-5 104 9 1 7-18 7 0-12s53-6 53-6"
                                                        />
                                                {/if}
                                        </g></svg
                                >
                        </span>
                        <span> inbox</span>
                </span>
                ?
        </p>
        <div class="email">
                <form>
                        <label for="email">Email</label>
                        <input
                                type="text"
                                placeholder="We saved a spot for your email"
                        />
                        <button type="submit">Send</button>
                </form>
                <p class="disclaimer">
                        By clicking send you'll receive occasional emails from
                        Spotify Design. You always have the choice to
                        unsubscribe within every email you receive.
                </p>
        </div>
</div>

<style>
        svg.arrow,
        svg.swirl {
                position: absolute;
                height: 100px;
                color: yellow;
        }
        svg.swirl {
                left: -20px;
                top: -10px;
        }
        svg.arrow {
                transform: rotate(20deg);
                height: 80px;
                top: 100px;
                left: 90px;
        }
        .email {
                grid-area: form;
        }
        span.stroke {
                position: relative;
        }
        p.disclaimer {
                color: rgb(131, 126, 126);
                font-size: 14px;
                margin-top: 8.75rem;
                line-height: 1.29;
                letter-spacing: -0.04em;
        }
        form {
                border-bottom: 1px solid white;
                display: grid;
                grid-template-columns: 0px auto max-content;
        }
        input {
                font-size: 24px;
                background-color: transparent;
                color: white;
                border: 0;
                line-height: 48px;
                letter-spacing: -0.04em;
                color: white;
                font-weight: 300;
        }
        input:focus {
                outline: none;
        }
        input::placeholder {
                color: white;
                opacity: 1;
        }
        label {
                overflow: hidden;
        }
        button {
                color: white;
                background-color: transparent;
                border: 0;
                text-transform: uppercase;
        }
        p.cta {
                grid-area: cta;
                font-size: 56px;
                font-weight: 700;
        }
        .container {
                font-family: "CircularSpotifyText", -apple-system,
                        BlinkMacSystemFont, sans-serif;
                padding: 5rem;
                background: black;
                color: white;
                display: grid;
                grid-template-columns: 3fr 2fr;
                grid-template-areas:
                        "cta none"
                        "cta form";
                grid-template-rows: 300px auto;
        }
</style>
