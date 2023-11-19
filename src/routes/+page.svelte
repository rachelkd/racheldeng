<script lang="ts">
    import IconsBar from "./_components/IconsBar.svelte";
    import Welcome from "./_components/WelcomeText.svelte";
    import NavBar from "./_components/NavBar.svelte";
    import AboutMe from "./about/+page.svelte";
    // import { afterUpdate } from 'svelte';
    // import { goto } from '$app/navigation'
    import { fade, fly } from 'svelte/transition';
    // import { quintOut } from 'svelte/easing';
    import { onMount, onDestroy } from 'svelte';

    // ---------- Variables -----------------
    // Variables for showing elements
    let showWelcome = false;
    let showSummary = false;
    const showSummaryKey = 'showSummary';
    
    // ------------ Event handlers ---------------
    // Handle key presses (Enter => show summary)
    function handleKeyDown(event: KeyboardEvent) {
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
    // Handle start button pressed (on enter or click)
    //      set showSummary = true, update in local storage
    function startBtnPressed() {
        // If showSummary is false, update to true. Do not change again.
        if (!showSummary) {
            showSummary = true;
            updateShowSummary(true); // Keys value in local storage
        }
    }
    // Handles clicks (Start-btn => show summary)
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
    
    // ----------- Functions ------------
    // Updates showSummary localStorage value
    function updateShowSummary(value=false) {
        localStorage.setItem(showSummaryKey, JSON.stringify(value));
    }
    // Gets showSummary from local storage
    function getShowSummary() {
        const storedValue = localStorage.getItem(showSummaryKey);
        if (storedValue === null) {
            return;
        }
        showSummary = JSON.parse(storedValue);
    }

    // -------- Lifecycle functions --------
    // onMount: Log status, set showWelcome to true, 
    // Get showSummary value from local storage
    onMount( () => {
        console.log("Homepage loaded successfully!");
        // Fade in the welcome text
        showWelcome = true;
        // Check if start button has already been clicked (in local storage)
        getShowSummary();
    });
    // Get rid of showSummary in local storage
    // onDestroy( () => {
    //     // localStorage.removeItem(showSummaryKey);
    // });

</script>

<!-- <div in:fade={{ delay: 350, duration: 1500 }} out:fly={{ delay: 100, duration: 800, y: -500, opacity: 0.1, easing: quintOut }}> -->

<!-- Get rid of out transition for now -->
{#if showWelcome}
<div in:fade={{ delay: 350, duration: 1500 }}>
    <Welcome {handleClick} {showSummary} />
</div>
{/if}

{#if showSummary}
    <div class="page" in:fade={{delay: 300, duration: 1000}}>
        <div class="about-me-box">
            <p>I am a first year computer science student at University of Toronto. I love everything technology -- whether it&rsquo;s to do with healthcare, education, music, or visual media.</p>
            <br>
            <a class="icon-btn" href="mailto:rachel05deng@gmail.com"><button class="contact-me-btn">contact me</button></a>
        </div>
        <!-- <NavBar /> -->
    </div>
    <div in:fade={{delay: 500, duration: 1000}}>
        <NavBar />
    </div>
{/if}

<IconsBar />

<svelte:window on:keydown={handleKeyDown} />