<script>
    let imageUrl = 'kneexraygoogle.jpg';
    
    let activeBox = null;

    function setActiveBox(boxName) {
        activeBox = boxName;
    }

    function clearActiveBox() {
        activeBox = null;
    }
</script>

<style>
    :global(body), :global(html) {
        margin: 0;
        padding: 0;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        background-color: #000033;
    }

    .body {
        display: flex;
        justify-content: space-around;
        align-items: stretch;
        height: calc(100vh - 50px);
        width: 100%;
        padding: 20px 0;
    }
  
    .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 50%;
        padding: 10px;
        box-sizing: border-box;
    }

    img {
        max-width: 100%;
        max-height: 100%;
        object-fit: contain;
    }

    .text-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100%;
        text-align: center;
        padding: 0 20px 20px;
        overflow-y: auto;
        background-color: white;
        color: black;
        margin: 0 100px 100px;
    }

    .overlay {
        position: absolute;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(3, 1fr);
        width: 100%;
        height: 100%;
        top: 0;
        pointer-events: none;
    }

    .box {
        border: 2px solid transparent;
    }

    .box.upper-middle { grid-area: 1 / 2; }
    .box.middle-middle { grid-area: 2 / 2; }
    .box.lower-middle { grid-area: 3 / 2; }

    .active {
        border-color: green;
    }

    /* Specific alignment for the first paragraph (Briefkopf) */
    .text-container p:first-child {
    text-align: left;
    align-self: flex-start;
    width: 100%;
    }

    p.hover.upperbox:hover { cursor: pointer; }
    p.hover.middlebox:hover { cursor: pointer; }
    p.hover.lowerbox:hover { cursor: pointer; }
</style>

<div class="body">
    <div class="container image-container" style="position: relative;">
        <img src={imageUrl} alt="Knee X-ray">
        <div class="overlay">
            <div class="box upper-middle" class:active={activeBox === 'upper-middle'}></div>
            <div class="box middle-middle" class:active={activeBox === 'middle-middle'}></div>
            <div class="box lower-middle" class:active={activeBox === 'lower-middle'}></div>
        </div>
    </div>
    <div class="container text-container">
        <p>Briefkopf</p>
        <p class="hover upperbox" on:mouseenter={() => setActiveBox('upper-middle')} on:mouseleave={clearActiveBox}>On the lateral side of the femur a bony protuberance is visible.</p>
        <p class="hover middlebox" on:mouseenter={() => setActiveBox('middle-middle')} on:mouseleave={clearActiveBox}>The epicondiles are in good shape.</p>
        <p class="hover lowerbox" on:mouseenter={() => setActiveBox('lower-middle')} on:mouseleave={clearActiveBox}>The joint gap is even and shows no signs of erosion.</p>
    </div>
</div>
