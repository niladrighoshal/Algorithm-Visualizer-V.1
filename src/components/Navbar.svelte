<script>
    import { Router, link } from "svelte-routing";
    import { ActiveVisualizer } from "../stores/active-visualizer";
</script>

<nav>
    <div id="desktop-nav">
        <Router>
            <a href="/" use:link on:click={() => ActiveVisualizer.set("")}>
                <h3>
                    Algorithm Visualizer
                    <span class="animate-text-gradient"> 1.0 </span>
                </h3>
            </a>
        </Router>
        <Router>
            <div class="links" id="desktop-links">
                <a  use:link href="sorting"
                    class:activeRoute={$ActiveVisualizer == "sorting"}>
                    Sorting </a>

                <a  use:link href="searching"
                    class:activeRoute={$ActiveVisualizer == "searching"}>
                    Searching </a>

                <a  use:link href="path-finding"
                    class:activeRoute={$ActiveVisualizer == "path-finding"}>
                    Path Finding </a>
            </div>
        </Router>
        <a  target="_blank"
            title="Niladri Ghoshal"
            name="Niladri Ghoshal"
            href="https://github.com/niladrighoshal">
            <img
                src="./assets/me.png"
                class="avatar"
                alt="niladrighoshal avatar" />
        </a>
    </div>
    <div id="mobile-nav">
        <Router>
            <div class="links">
                <a  use:link href="sorting"
                    class:activeRoute={$ActiveVisualizer == "sorting"}>
                    Sorting </a>

                <a  use:link href="searching"
                    class:activeRoute={$ActiveVisualizer == "searching"}>
                    Searching </a>
                    
                <a  use:link href="path-finding"
                    class:activeRoute={$ActiveVisualizer == "path-finding"}>
                    Path Finding </a>
            </div>
        </Router>
    </div>
</nav>

<style>
    nav {
        /* background-color: var(--surface3); */
        background: linear-gradient(var(--surface3), var(--surface2));
        padding: .75rem 1.5rem;
        box-shadow: 0 -8px 16px 16px rgba(0, 0, 0, .2);
        z-index: 4;
    }
    #desktop-nav {
        display: flex;
        place-content: center space-between;
        place-items: center;
    }
    .links {
        display: flex;
        place-content: center;
        align-items: center;
        background: linear-gradient(var(--surface4),var(--surface3));
        box-shadow: 0 2px 2px 2px rgba(0, 0, 0, .1);
    }
    .links a {
        padding: .5rem 1.3rem;
        border-radius: .25rem;
        color: var(--text1);
    }
    #mobile-nav {
        display: none;
        margin-top: 1rem;
    }
    @media (max-width: 700px) {
        #desktop-links {
            display: none;
        }
        #mobile-nav {
            display: inline-block;
            position: relative;
            left: 50%;
            transform: translateX(-50%);
        }
        #mobile-nav .links {
            place-content: start;
        }
        #mobile-nav .links a {
            padding: .5rem 1rem;
        }
    }
    @media (max-width: 500px) {
        nav {
            padding: .75rem 1rem;
        }
    }
</style>
