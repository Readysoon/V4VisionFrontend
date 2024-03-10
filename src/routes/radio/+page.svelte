<script>
    let imageUrl = 'kneexraygoogle.jpg';
    /** @type {string|null} */
    let activeBox = null; // Determines which box is highlighted based on the paragraph hovered

    /**
    * Define a function to update the activeBox
    * @param {number} index - The index to check
    */

    // Define a function to update the activeBox
    function updateActiveBox(index) {
        if ([1, 2, 3].includes(index)) {
            activeBox = 'upper-middle';
        } else if ([4, 5, 6].includes(index)) {
            activeBox = 'middle-middle';
        } else if ([7, 8, 9].includes(index)) {
            activeBox = 'lower-middle';
        }
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
        {#each Array(9).fill(0) as _, index (index)}
            <p class={(index + 1).toString()} on:mouseenter={() => updateActiveBox(index + 1)} on:mouseleave={clearActiveBox}>
                {`Paragraph ${index + 1}`}
            </p>
        {/each}
    </div>
</div>
