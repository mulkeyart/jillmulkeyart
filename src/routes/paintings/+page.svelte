<script>
	import Cards from '../../lib/Components/Cards.svelte';
	import { images } from '../../lib/constants';
</script>

<div class="paintings_container mx-auto p-2 mt-n1 row row-cols-1 row-cols-md-2 row-cols-lg-3">
	{#each images as image, index}
		<Cards
			title={image.title}
			subtitle={image.subtitle}
			cardText={image.cardText}
			cardImage={image.imageSrc}
		/>
	{/each}
</div>

<style>
	/* .paintings_container{
        width: 400px;
        height: 400px;
    } */
</style>
