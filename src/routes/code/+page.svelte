<script>
    function navigateTo(url) {
        window.open(url, '_blank').focus();
    }
</script>

<div class="page">
    <h1>PROGRAMMING</h1>
    <br>
    <div class="codeGrid">
        <div class="cell">
            <h2>This Site</h2>
            <img class="thumbnail"src="codeThumbnails/namesakeThumb.png" alt="This Site Thumbnail" onclick={navigateTo("https://github.com/Iyan-SM/Namesake")}>
            <div class="icon-row"><img class="icon" src="codeThumbnails/svelte.png" alt="svelte"><p>SvelteKit</p></div>
        </div>
        <div class="cell">
            <h2>Computer Vision</h2>
            <img class="thumbnail"src="codeThumbnails/visionportal.png" alt="Computer Vision Thumbnail" onclick={navigateTo("https://github.com/IFC-Robotics/Center-Stage_2023-2024")}>
            <div class="icon-row"><i class="fa-brands fa-java Java icon"></i><p>Java</p></div>
        </div>
        <div class="cell">
            <h2>Summer Game</h2>
            <img class="thumbnail"src="codeThumbnails/summerGame.png" alt="Summer Game Thumbnail" onclick={navigateTo("https://github.com/Iyan-SM/Summer-Game")}>
            <div class="icon-row"><img class="icon" src="codeThumbnails/Godot_icon.png" alt="godot"><p>Godot</p></div>
        </div>       
        <div class="cell">
            <h2>Event Booking Demo Site</h2>
            <img class="thumbnail"src="codeThumbnails/eventBookerThumb.png" alt="Event Booking Thumbnail" onclick={navigateTo("https://github.com/ElliottCepin/event-booking")}>
            <div class="icon-row"><img class="icon" src="codeThumbnails/mongodb-icon.png" alt="mongoDB"><p>MongoDB</p></div>
        </div>      

    </div>
</div>

<style>
    
    h1 {
        padding-left: 20px;
        color: black;
        text-shadow: grey 1px 1px 2px;
    }

    h2 {
        color: var(--template-purple-shadow);
        margin: 0px;
    }
    .page{
        height: calc(100vh - 40px);
        width: calc(100vw - 40px);
        padding: 20px;

    }
    .codeGrid {
        width: 60vw;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content:space-between;
        margin-left: 10vw;
    }
    
    .cell {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        background-color: white;
        position: relative;
        margin: 0px 20px 20px 20px;
    }

    .thumbnail {
        width: 300px;
        height: 180px;
        margin-bottom: 2px;
        z-index: 0;
        border: 4px solid #4c286a;
        border-radius: 10px;
        box-shadow: .1rem .1rem 0.5rem lightgrey;
        transition: box-shadow ease 0.5s, border ease 0.5s;

    }

    /* for rounded border */
    .thumbnail::after {
        content:"";
        width: 300px;
        height: 180px;
        position: absolute;
        border: 4px solid #4c286a;
        border-bottom-width: 2px;
        border-radius: 10px 10px 0px 0px;
        left: -4px;
        top: -4px;
        z-index: 1;
    }

    .thumbnail:hover {
        box-shadow:  -.25rem -.25rem 0.5rem var(--template-orange), .25rem .25rem 0.5rem var(--template-orange);
        border: 4px solid var(--template-pink);
    }

    .icon-row{
        display: flex;
        flex-direction: row;
        align-items: center;

    }

    a {
        color: var(--template-purple);
        padding-top: 10px;
        padding: 5px;

    }
    a:not(.deactivated):hover {
        text-decoration: underline;
    }

    .Java {
        color: darkred;
    }

    .icon {
        position: relative;
        width: 18px;
        height: 18px;
        z-index: 1;
        margin: 5px;
        font-size: 20px;
    }

    @media screen and (max-width: 1160px) {
        h1 {
            margin-top: 14rem;
            text-align: center;
        }
        .codeGrid {
            width: 100%;
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content:space-around;
            align-items: center;
            margin-left: 0;
        }
    }
</style>