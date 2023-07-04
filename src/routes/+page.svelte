<script>
    import IconsBar from "./components/IconsBar.svelte";
    import Welcome from "./components/WelcomeText.svelte";
    import NavBar from "./components/NavBar.svelte";
    import AboutMe from "./about/+page.svelte";
    // import { afterUpdate } from 'svelte';
    import { goto } from '$app/navigation'
    import { fade, fly } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
    import { onMount } from 'svelte';

    let showWelcome = false;
    let showElements;
    
    function handleKeyDown(event={}) {
        // Log key
        // console.log(event.key.toLowerCase());
        switch(event.key.toLowerCase()) {
            case "enter":
                startBtnPressed();
                break;
            default:
                break;
        }
    }

    function startBtnPressed() {
        // showWelcome = false;
        showElements = true;
        // goto("/about");
    }

    function handleClick(id="") {
        console.log(id);
        switch(id) {
            case "start-btn":
                startBtnPressed();
                break;
            default:
                break;
        }
    }

    // Lifecycle functions
    onMount( () => {
        showWelcome = true;
    });
</script>

<!-- <div in:fade={{ delay: 350, duration: 1500 }} out:fly={{ delay: 100, duration: 800, y: -500, opacity: 0.1, easing: quintOut }}> -->
<!-- Get rid of out transition for now -->
{#if showWelcome}
<div in:fade={{ delay: 350, duration: 1500 }}>
    <Welcome {handleClick} {showElements} />
</div>
{/if}
{#if showElements}
    <div class="page" in:fade={{delay: 300, duration: 1000}}>
        <div class="about-me-box">
            <p>I am a first year computer science student at University of Toronto. I love everything technology -- whether it&rsquo;s to do with healthcare, education, music, or visual media.</p>
            <br>
            <a class="icon-btn" href="mailto:rachel05deng@gmail.com"><button class="contact-me-btn">contact me</button></a>
        </div>
        <NavBar />
    </div>
{/if}
<!-- {#if showWelcome}
    <div in:fade={{ delay: 350, duration: 1500 }} out:fly={{ delay: 100, duration: 800, y: -500, opacity: 0.1, easing: quintOut }}>
        <Welcome {handleClick} />
    </div>
    {:else if showElements}
    <div class="page" in:fade={{delay: 300, duration: 1500}}>
        <div class="about-me-box">
            <p>I am a first year computer science student at University of Toronto. I love everything technology -- whether it's to do with healthcare, education, music, or visual media.</p>
            <a class="icon-btn" href="mailto:rachel05deng@gmail.com"><button class="contact-me-btn">contact me</button></a>
        </div>
</div>
{/if} -->

<IconsBar />

<svelte:window on:keydown={handleKeyDown} />