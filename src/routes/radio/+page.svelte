<script>
    let imageUrl = 'kneexraygoogle.jpg';
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
        padding: 10px; /* This padding applies to the content inside the container. */
        box-sizing: border-box;
    }

    img {
        max-width: 100%;
        max-height: 100%;
        object-fit: contain;
    }

    .text-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        text-align: center;
        padding: 0 20px 20px;
        overflow-y: auto;
        background-color: white;
        color: black;
        margin: 0 100px 100px; /* Add left, right, and bottom margins to the text container */
    }
</style>

<div class="body">
    <div class="container image-container">
        <img src={imageUrl} alt="Knee X-ray">
    </div>
    <div class="container text-container">
        <p class="1">Der Gelenkspalt ist nicht verkleinert</p>
        <p class="2">Keine Fraktur erkennbar</p>
        <p class="3">keine rechts/links fehlstellung</p>
        <p class="4">test test test </p>
        <p class="5">ok ok ok</p>
        <p class="6">Keine Fraktur erkennbar</p>
        <p class="7">keine rechts/links fehlstellung</p>
        <p class="8">test test test </p>
        <p class="9">ok ok ok</p>
    </div>
</div>

make an overlay for the image which has 9 divs in 3 rows and 3 boxes with green margins for each box. the margins should be hidden