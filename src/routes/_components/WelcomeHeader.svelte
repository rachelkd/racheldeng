<a class="header" href="/">
    <div class="welcome-box">
        <h1>nice to meet you!<br>my name is <span class=highlight>rachel</span>.</h1>
    </div>
</a>



<style>
    .header {
        position: fixed;
        top: 1rem;
        width: 100vw;
        height: auto;
        padding-bottom: 1rem;
        background-color: var(--color-bg);
        color: inherit;
        text-decoration: inherit;
    }

    .welcome-box {
        position: relative;
        -webkit-touch-callout: none; /* iOS Safari */
        -webkit-user-select: none; /* Safari */
        -khtml-user-select: none; /* Konqueror HTML */
        -moz-user-select: none; /* Old versions of Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
        user-select: none; /* Non-prefixed version, currently supported by Chrome, Edge, Opera and Firefox */
    }

    .welcome-box h1 {
        font-size: 1vw; 
        /* was 18px before */
        white-space: nowrap;
    }
    .welcome-box h1::after {
    content: "";
    margin-left: 0.25rem;
    width: 0.1rem;
    height: 15px;
    border-radius: 5px;
    background: var(--color-text);
    display: inline-block;
    animation: cursor-blink 1.5s ease-in-out infinite;
    }
    
</style>