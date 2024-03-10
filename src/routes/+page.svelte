<script>
	let imageUrl = 'kneexraygoogle.jpg';
	let loadingGif = '1494(1).gif';
	let showContent = false;

	function upload() {
		setTimeout(() => {
			showContent = true;
		}, 2000);
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
	  width: calc(100% - 40px);
	  flex-grow: 1;
	  display: flex;
	  justify-content: space-around;
	  align-items: center;
	  height: calc(100vh - 50px - 40px);
	}
  
	.container {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  width: calc(50% - 20px);
	  height: 100%;
	  flex-direction: column;
	  overflow: hidden;
	}

    p {
        color: white;
    }

	img, button {
	  max-height: 80%;
	  max-width: 90%;
	}
</style>

<div class="body">
	<div class="container">
		{#if showContent}
			<img src={imageUrl} alt="Knee X-ray">
		{:else}
			<button on:click={upload}>Upload</button>
		{/if}
	</div>
	<div class="container">
		{#if showContent}
			<img src={loadingGif} alt="Loading">
            <p>You are on position: 1</p>
		{/if}
	</div>
</div>