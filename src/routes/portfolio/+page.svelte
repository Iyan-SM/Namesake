<div class="page">
    <h1>PORTFOLIO</h1>
    <div class="artGrid">
        <div class="cell">
            <img class="artwork" src="art/chaor3.png" alt="Chair Render">
            <p class="title">Chair 3</p>
            <p class="desc">asset</p>
        </div>
        <div class="cell">
            <video class="artwork" src="art/solarSoup.mov" alt="Planets Orbiting In Solar Ocean Animation" autoplay loop muted webkit-playsinline playsinline><track kind="captions"></video>
            <p class="title">Solar Soup</p>
            <p class="desc">animation, simulation</p>
        </div>
        <div class="cell">
            <img class="artwork" src="art/bestagon.gif" alt="Rotating Hexagon Render">
            <p class="title">Bestagon</p>
            <p class="desc">procedural generation</p>
        </div>
        <div class="cell">
            <img class="artwork" src="art/bulldog_v3.png" alt="Bulldog Logo Render">
            <p class="title">Bulldog Logo</p>
            <p class="desc">icon</p>
        </div>
        <div class="cell">
            <img class="artwork" src="art/oneOne.png" alt="One-One Render">
            <p class="title">One-One</p>
            <p class="desc">character</p>
        </div>
        
        <div class="cell">
            <video class="artwork" src="art/oshkosh_v3.mp4" alt="Cell Shaded Train Animation" autoplay loop muted webkit-playsinline playsinline><track kind="captions"></video>
            <p class="title">Osh Kosh</p>
            <p class="desc">animation, cell Shading</p>
        </div>
        <!-- <div class="cell">
            <img class="artwork" src="" alt="ADD Brick Wall">
            <p class="title">Brick</p>
            <p class="desc">procedural generation</p>
        </div> -->
    </div>
</div>

<style>
    h1 {
        padding-left: 20px;
        color: black;
        text-shadow: grey 1px 1px 2px;
    }
    .page{
        height: 98vh;
        width: calc(100% - 40px);
        /* background-image: url(paper.png); */
        padding: 20px;
    }

    .artGrid{
        width: 76vw;
        padding-bottom: 20px;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
    }

    .cell {
        text-align: center;
    }

    .artwork {
        height: 300px;
        padding: 22px;
        margin: 20px;
        background-color: #c787a1;
        box-shadow:
            3px 3px  10px, 
            inset #4c286a 0 0 0 5px, 
            inset #7E52A0 0 0 0 1px, 
            inset #7E52A0 0 0 0 10px, 
            inset #9d76bb 0 0 0 11px, 
            inset #D295BF 0 0 0 16px, 
            inset #dfafc3 0 0 0 17px, 
            inset #E6BCCD 0 0 0 21px, 
            inset #c787a1 0 0 0 22px;
    }

    .title {
        font-size: 25px;
        color: #4c286a;
        margin: 0;
    }

    .desc {
        font-size: 18px;
        color: grey;
        margin: 0;
    }

    @media screen and (max-width: 1160px) {
        h1 {
            margin-top: 14rem;
            text-align: center;
        }
        .artGrid{
            width: 100%;
            padding-bottom: 20px;
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            justify-content: space-around;
            align-items: center;
        }
    }

     @media screen and (max-width: 656px) {
        .artwork {
            width: calc(100vw - 124px);
            height: auto;
        }
    }

</style>