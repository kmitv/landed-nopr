<script lang="ts">
	import MainCentral from './components/MainCentral/MainCentral.svelte';

	const backgroundSrc = 'images/background.jpg';
</script>

<main>
	<img src="{backgroundSrc}" alt="background" class="background-image" />
	<MainCentral />
</main>

<style>
	main {
		display: flex;
		align-items: center;
		justify-content: center;
		height: 100vh;
		width: 100vw;
		position: absolute;
		max-width: none;
		overflow: hidden;
	}
</style>