<script>
    // import IconButton from '@smui/icon-button';
    import SvgIcon from '@jamescoyle/svelte-icon';
    import { mdiEmailOpenHeartOutline, mdiGit, mdiLinkedin } from '@mdi/js';
    
    let clicks = 0;
    // Functions
    function handleClick(icon = "") 
    {
        clicks++;
        switch(icon) 
        {
            case "mail":
                console.log("Redirecting to mail...");
                break;
            case "git":
                console.log("Redirecting to Github...");
                window.open("https://github.com/rachelkd/");
                break;
            case "linkedin":
                console.log("Redirecting to LinkedIn...");
                window.location.href = "https://www.linkedin.com/in/rachelden/";
                break;
        }
        console.log({clicks});
    }
</script>

<div class="icons">
    <a class="icon-btn" href="mailto:rachel05deng@gmail.com"><SvgIcon type="mdi" path={mdiEmailOpenHeartOutline} size=32/></a>
    <button class="icon-btn" on:click={() => handleClick("git")}><SvgIcon type="mdi" path={mdiGit} size=32/></button>
    <button class="icon-btn" on:click={() => handleClick("linkedin")}><SvgIcon type="mdi" path={mdiLinkedin} size=32/></button>
</div>

<style>
    .icons {
        position: fixed;
        display: flex;
        bottom: 1.8rem;
        right: 0;
        padding: 1rem;
    }
    .icon-btn {
    width: auto;
    height: auto;
    align-items: center;
    justify-content: center;
    outline: none;
    padding-left: 0;
    padding-right: 1rem;
    border: 0;
    color: var(--color-2);
    transition: all .5s ease;
}
    .icon-btn:hover {
        color: var(--color-h);
        transition: all .2s ease;
        cursor: pointer;
    }
</style>