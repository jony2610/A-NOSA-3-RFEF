<script lang="ts">
	import favicon from '$lib/assets/favicon.ico';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}


<style>

	:global(*) {
	  margin: 0;
	  padding: 0;
	  outline: 0;
	  box-sizing: border-box;
	}
	
	:global(html){
		font-size: 16px;
		scroll-behavior: smooth;
	}

	:global(body){
	 background:url(/assets/img/campo_de_futbol.avif);
	 background-repeat: no-repeat;
	 background-position: center;
	 background-size: cover;
	 color: white;
	 height: 109vh;
	 -webkit-font-smoothing: antialiased;
	}
	
	:root{
		--color-primary:white;
		--color-secundary:red;
	}

	:global(body, input, button) {

	 font-family:'Times New Roman', Times, serif ;
	}
	
	:global(button) {
	 cursor: pointer;
	}

	@font-face{
		font: family EASPORTS 15ttf;
		src: url(./Fonts/ea_font/EASPORTS15.ttf)}
</style>