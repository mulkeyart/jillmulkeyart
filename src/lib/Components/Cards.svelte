<script>
	import {
		Button,
		Card,
		CardBody,
		CardFooter,
		CardHeader,
		CardSubtitle,
		CardText,
		CardTitle
	} from '@sveltestrap/sveltestrap';

	export let title = '';
	export let subtitle = '';
	export let cardText = '';
	export let cardImage = '';

	let isExpanded = false;

	function toggleExpansion() {
		isExpanded = !isExpanded;
	}

	function truncateText(text, maxLength) {
		if (text.length > maxLength) {
			return text.slice(0, maxLength) + '...';
		}
		return text;
	}
</script>

<div class="card-deck">
	<Card class="customCustom card bg-transparent border border-light rounded-lg cursor-pointer">
		<CardHeader>
			<CardTitle class="opacity-100 text-white" style="text-align: center;">{title}</CardTitle>
		</CardHeader>
		<CardBody class="text-center opacity-100">
			<img
				class="cardImage mb-3 opacity-100"
				width="300px"
				height="300px"
				src={cardImage}
				alt="eachCardImage"
			/>
			{#if isExpanded}
				<CardSubtitle class="text-white"
					><span>
						<p on:click={toggleExpansion} class="font-white">{subtitle}</p>
					</span>
				</CardSubtitle>
			{:else}
				<CardSubtitle class="text-white">
					<span>
						<p on:click={toggleExpansion} class="font-white">{truncateText(subtitle, 20)}</p>
					</span>
				</CardSubtitle>
			{/if}
			<CardText class="text-white">{cardText}</CardText>
		</CardBody>
		<CardFooter class="text-center opacity-100 text-white">$289.99</CardFooter>
		<Button class="mx-auto d-block opacity-100">Add To Cart</Button>
	</Card>
</div>

<style>
	.customCustom {
		max-width: 300px;
		height: 200px; /* Set the desired height for the card */
		overflow: auto; /* Add scrollbars when content overflows */
	}
	CardSubtitle {
		font: white;
	}
</style>
