<script>
    import { fade, fly } from 'svelte/transition';
    import IconsBar from "../_components/IconsBar.svelte";
    import NavBar from "../_components/NavBar.svelte";
    import WelcomeHeader from "../_components/WelcomeHeader.svelte";
    // import { afterUpdate } from 'svelte';
    // import { goto } from '$app/navigation'
    // import { quintOut } from 'svelte/easing';
    // import { onMount } from 'svelte';
</script>

<WelcomeHeader />

<div class="page" in:fade={{delay: 300, duration: 1000}}>
    <h1>/about-me</h1>
    <div class="about-me-text">
        <p>Formally called <span class="highlight-2">Rachel Deng</span>. Pursuing an Honours Bachelor of Science in computer science with a minor in philosophy at <span class="highlight-2">University of Toronto</span>. Following developments in technology intersected with health and society.<br><br>Working with technologies in:</p>
        <table>
            <tr>
                <td>- Python</td>
                <td>- Java</td>
                <td>- JavaScript ES6+</td>
            </tr>
            <tr>
                <td>- Svelte.js</td>
                <td>- React.js</td>
                <td>- Processing</td>
            </tr>
            <tr>
                <td>- HTML & CSS</td>
                <td></td>
                <td></td>
            </tr>
            </table>
        <p>Peak Platinum 3 in Valorant. Thinks <i>folklore</i> is Taylor Swift&rsquo;s best album. Misses walking her dog with a roll of Gold 200 back home in Vancouver.</p>
    </div>
</div>
<IconsBar />


<NavBar />

<style>
    table {
        line-height: 150%;
    }
    td {
        padding-right: 4rem;
        /* padding-bottom: 0.5rem; */
    }
    .about-me-text {
        margin-right: 40vw;
    }
</style>