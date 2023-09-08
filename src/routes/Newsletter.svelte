<div class="container">
        <p class="cta">
                Want Spotify Design updates sent straight to your
                <span>
                        <span class="stroke"
                                ><svg
                                        xmlns="http://www.w3.org/2000/svg"
                                        viewBox="0 0 120 68"
                                        ><g
                                                fill="none"
                                                stroke="yellow"
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                ><path
                                                        d="M105 10C28-9-29 40 34 56c62 16 91-29 66-29"
                                                /><path
                                                        d="M109 16C82-20-56 21 30 55s105-27 75-45"
                                                /></g
                                        ></svg
                                ></span
                        >
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
        svg {
                position: absolute;
                left: -20px;
                top: -10px;
                height: 100px;
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
