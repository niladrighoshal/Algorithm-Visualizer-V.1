<script>
    import { onMount } from 'svelte';
    import { ActiveVisualizer } from '../../stores/active-visualizer';

    onMount(() => {
        ActiveVisualizer.set("");
    });
</script>
<main>
    <header>
        <h1 class="title"> Algorithm Visualizer <span class="animate-text-gradient"> 1.0 </span> </h1>
        <h2 class="sub-title"> An Interactive Visualization Tool. </h2>
        <!-- <h1 class="sub-title"> Input some data,  visualize, and analyze base on the results. </h1> -->
    </header>

    <section id="landing-page-animation">
        <div class="floor"></div>
    </section>

    <article id="about-this-app">
        <h1> About this App </h1>
        <p>
            Algorithm Visualizer is an interactive tool that showcases essential algorithms for Sorting, Searching, and Path Finding. It allows you to compare and observe the operations of various algorithms with engaging animations. You have the freedom to customize settings and inputs to suit your preferences. Through inputting data and analyzing the results, you can gain insights into the algorithms' efficiencies and make informed comparisons.
        </p>
    </article>

    <br>

    <article id="sorting-tutorial">
        <h1> Sorting Visualizer Tutorial </h1>
        <p>
            Feel free to click on the Sorting tab, where you'll find intuitive and enjoyable inputs and controls. If you prefer, you can also check out the instructional <a href="#sorting-video"> video below. </a>
        </p>

        <h3> What is Sorting Visualizer ? </h3>
        <p>
            Sorting visualizer allows you to compare sorting algorithms based on their speed. Watch how each algorithm perform and how they manage to sort the input array. A table depending on there speed is generated after all algorithms are finished.
        </p>
        <video controls id="sorting-video" muted>
            <source src="./assets/videos/sorting.mp4" type="video/mp4">
                <track kind="captions">
        </video>
    </article>

    <article id="searching-tutorial">
        <h1> Searching Visualizer Tutorial </h1>
        <p>
            Just like sorting visualizer the inputs and controls are pretty straight forward and fun to understand through visualization. You can go ahead and try it now or you can watch the <a href="#searching-video"> video below. </a>
        </p>

        <h3> What is Searching Visualizer ? </h3>
        <p>
            The Searching Visualizer enables you to compare and analyze various searching algorithms. It helps determine which algorithm is faster and provides insights into their respective use cases. By using this visualizer, you can discover the number of operations or steps each algorithm takes to find the search input or, if not found, the total operations completed during the search process. Understanding their differences becomes clearer through this interactive tool.
        </p>
        <video controls id="searching-video" muted>
            <source src="./assets/videos/searching.mp4" type="video/mp4">
                <track kind="captions">
        </video>
    </article>

    <article id="path-finding-tutorial">
        <h1> Path Finding Visualizer Tutorial </h1>
        <p>
            Unlike the first two visualizers, there are some important controls,and you need to learn them. I recommend watching the <a href="#path-finding-video"> video below. </a>
        </p>
        <video controls id="searching-video" muted>
            <source src="./assets/videos/path-finding.mp4" type="video/mp4">
                <track kind="captions">
        </video>
    </article>

    <article>
        <h1 class="title" style="text-align: center;"> Happy Visualizing! </h1>
    </article>
</main>

<style>

    #landing-page-animation {
        position: absolute;
        width: calc(100% + 1rem);
        height: 22rem;
        perspective: 17rem;
        perspective-origin: 50% 1rem;
        overflow: hidden;
        top: -5rem;
        left: -1rem;
        z-index: -1;
    }
    .floor {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        position: absolute;
        background-image: repeating-radial-gradient(var(--surface3), var(--surface1) 80%);
        background-size: 5rem 5rem;
        transform: rotateX(80deg);
        animation: rotateScene 25s infinite linear;
        box-shadow: inset 0 0 50px 85px var(--surface1);
    }

    @keyframes rotateScene {
        from { background-position-y: bottom; }
        to { background-position-y: top; }
    }
    

    header {
        margin-bottom: 2rem;
        padding: 1rem;
    }
    .title{
        font-size: 3rem;
        margin: .5rem 0;
    }
    .sub-title {
        color: var(--text2);
    }
    article, section {
        padding: 1rem;
    }
    a {
        color: dodgerblue;
    }
    article h1 {
        margin: 1rem 0 .5rem 0;
    }
    article h3 {
        margin: 1rem 0 .5rem 0;
        color: var(--text2);
    }
    article video {
        width: 100%;
        display: block;
        margin: 2rem auto ;
    }
    article:target {
        animation: notice 4s ease;
    }
    @keyframes notice {
        from { background-color: var(--surface3); }
        to { background-color: inherit; }
    }
    @keyframes noticeText {
        to { color: var(--brand); }
    }
    @media (max-width: 900px) {
        header * {
            text-align: center;
        }
        article:target {
            animation: none;
        }
        article:target > h1 {
            animation: noticeText 4s ease;
        }
    }
    @media (max-width: 540px) {
        .title {
            font-size: 2rem;
        }
        article, section {
            padding: 1rem 0;
        }
        article video {
            width: 100%;
            display: block;
            margin: 2rem auto 3rem auto;
        }
    }
</style>