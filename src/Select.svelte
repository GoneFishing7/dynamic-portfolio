<script>
	import { onMount } from "svelte";
	import Card from "./Card.svelte";

	let cards = [
		{
			title: "Personality Reflection Assignment",
			imgSrc:
				"https://i5.walmartimages.com/asr/0f85cdab-896a-4a42-9fa6-fb2940363e8d.e257a24c7ebb92c74a8169f610d8bebd.jpeg",
			content: "An assignment of introspection and self-discovery",
			visible: false,
			link: "https://docs.google.com/document/d/1Uvyg0YsH9uMRM5G9j8R7MW9YY5hoDY7X/edit?usp=sharing&ouid=111362065916405916030&rtpof=true&sd=true",
			type: "a",
		},
		{
			title: "The Mediator",
			imgSrc:
				"https://www.16personalities.com/static/images/personality-types/avatars/faces/infp-mediator-s3-v1-male.svg?v=2",
			content: "My MBTI Results from 16Personalities",
			visible: false,
			link: "https://www.16personalities.com/infp-personality",
			type: "a",
		},
		{
			title: "Course Planner",
			imgSrc:
				"https://th.bing.com/th/id/OIP.wiL1U19HO4gmXbdLzYsPiAHaHu?pid=ImgDet&rs=1",
			content: "The courses I planned out for my time in the HCOS Grad Program",
			visible: false,
			link: "https://docs.google.com/document/d/1e-4T7DMPWeaeLZuPknp_A7yk40D-syQP_g2Y3uzMdfs/edit?usp=sharing",
			type: "b",
		},
		{
			title: "Career Research Assignment",
			imgSrc:
				"https://th.bing.com/th/id/OIP.Stzw-AJdZW4_xyKwjoN7wAHaE8?pid=ImgDet&rs=1",
			content: "I researched a few careers that I might be interested in",
			visible: false,
			link: "https://docs.google.com/document/d/1egeCqk07i2SGFlO6Vd_0_wpjLrGGoIO6saWwqE_DMfY/edit?usp=sharing",
			type: "b",
		},
		{
			title: "My Resume",
			imgSrc:
				"https://i.etsystatic.com/14806004/r/il/4fb257/4485011344/il_794xN.4485011344_ldzy.jpg",
			content: "A resume I created and used to apply for a job",
			visible: false,
			link: "https://docs.google.com/document/d/1ZX7Gc1qhKM9xBCQ4ymblHg_IAbiGuui_qC960Jk_cks/edit?usp=sharing",
			type: "c",
		},
		{
			title: "My Cover Letter",
			imgSrc:
				"https://th.bing.com/th/id/OIP.97L4QvjEjrupLxIbJwQn3QHaFY?pid=ImgDet&rs=1",
			content:
				"A mock cover letter that I created for my future self (when I finish university)",
			visible: false,
			link: "https://docs.google.com/document/d/1ETZm-8BYyOZ_ugbiknWM6aKRPHTQ9EyhIPXhm-PJHw8/edit?usp=sharing",
			type: "c",
		},
		{
			title: "Mapping My Week",
			imgSrc:
				"https://th.bing.com/th/id/OIP.QRl08nbftAy2YRwCbFUMOwHaHY?pid=ImgDet&rs=1",
			content:
				"I mapped out a typical week for the sake of reflection and, ultimately, better time management",
			visible: false,
			link: "https://drive.google.com/file/d/1MbIKpJhgMpVuzmUWwOD8vXmF1SKMV2Hb/view?usp=sharing",
			type: "d",
		},
		{
			title: "Post-Secondary Budget",
			imgSrc:
				"https://th.bing.com/th/id/OIP.OHhOvf0hi8NwHVKw0cUtxwHaFS?pid=ImgDet&rs=1",
			content: "A mock budget that I created for when I'm in university",
			visible: false,
			link: "https://docs.google.com/spreadsheets/d/1NUaXlfAKXH6p26g57gLG8eBgkOcnsIwHzG1bJREr4Fo/edit?usp=sharing",
			type: "d",
		},
	];
	onMount(async () => {
		let delay = 300;
		for (let i = 0; i < cards.length; i++) {
			setTimeout(() => {
				cards[i].visible = true;
				console.log(i);
			}, i * delay);
		}
	});
</script>

<div class="select">
	<div class="cards">
		{#each cards as card}
			<Card params={card} />
		{/each}
	</div>
</div>

<style>
	.select {
		display: flex;
		flex-direction: column;
		justify-content: center;
		max-width: 1333px;
	}
	.cards {
		margin-left: 0;
		margin-right: 0;

		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		align-content: center;
		gap: 20px;
	}
</style>
