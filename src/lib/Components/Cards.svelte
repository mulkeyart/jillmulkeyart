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
</script>

<!-- <Card>
    <CardHeader>
      <CardTitle style="text-align: center;">{title}</CardTitle>
    </CardHeader>
    <CardBody>
      <img class="cardImage" width='300px' height='300px' src={cardImage} alt="eachCardImage"/>
      <CardSubtitle style="text-align: center; max-width:300px;">{subtitle}</CardSubtitle>
      <CardText style="text-align: center;">{cardText}</CardText>
    </CardBody>
    <CardFooter style="text-align: center;">$289.99</CardFooter>
    <Button>Add To Cart</Button>
  </Card> -->
<div class="card-deck">
	<Card class="customCustom card bg-transparent border border-light rounded-lg cursor-pointer">
		<CardHeader>
			<CardTitle class="opacity-100" style="text-align: center;">{title}</CardTitle>
		</CardHeader>
		<CardBody class="text-center opacity-100">
			<img
				class="cardImage mb-3 opacity-100"
				width="300px"
				height="300px"
				src={cardImage}
				alt="eachCardImage"
			/>
			<CardSubtitle>{subtitle}</CardSubtitle>
			<CardText>{cardText}</CardText>
		</CardBody>
		<CardFooter class="text-center opacity-100">$289.99</CardFooter>
		<Button class="mx-auto d-block opacity-100">Add To Cart</Button>
	</Card>
</div>


<style>
 
  .customCustom {
    max-width: 300px;
    height: 200px; /* Set the desired height for the card */
    overflow: auto; /* Add scrollbars when content overflows */
  }
</style>