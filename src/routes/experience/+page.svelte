<script>
    import IconsBar from "../_components/IconsBar.svelte";
    import NavBar from "../_components/NavBar.svelte";
    import WelcomeHeader from "../_components/WelcomeHeader.svelte";
    import { fade } from 'svelte/transition';
    // import { afterUpdate } from 'svelte';
    // import { goto } from '$app/navigation'
    // import { quintOut } from 'svelte/easing';
    // import { onMount } from 'svelte';
</script>

<WelcomeHeader />

<div class="page" in:fade={{delay: 300, duration: 1000}}>
    <h1 class="error">Uh oh! Still working on this. See my <a href="http://linkedin.com/in/rachelden/" target="_blank" rel="noreferrer noopener">LinkedIn</a> for now.</h1>
</div>

<IconsBar />


<NavBar />

<style>
    .error a {
        text-decoration: underline;
        transition: all .2s ease;
    }
    .error a:hover {
        color: var(--color-h);
    }
</style>