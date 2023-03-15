<script>
	export let params;

	function link() {
		window.open(params.link, "_blank");
	}
</script>

<div
	on:click={link}
	class={`card ${params.visible ? "" : "hidden"} card-type-${params.type}`}
>
	<img src={params.imgSrc} alt={params.title} />
	<div class={`card-content`}>
		<h2>{params.title}</h2>
		<div class="card-content-main">
			{params.content}
		</div>
	</div>
</div>

<style>
	.hidden {
		opacity: 0;
		transform: scale(0.3);
		transition: 0.3 ease-out;
	}

	.card {
		background-color: rgb(27, 18, 34);
		border: 1px solid #141533;
		box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.808);
		border-radius: 8px;
		max-width: 250px;
		max-height: 450px;
		padding: 0;
		transition: 0.3s;
	}

	.card:hover {
		cursor: pointer;
		border-color: #646cff;
		box-shadow: 0 8px 64px 0 rgba(0, 0, 0, 0.918);
	}

	.card-type-b:hover {
		border-color: #ff8864;
	}

	.card-type-c:hover {
		border-color: #d364ff;
	}

	.card-type-d:hover {
		border-color: #3feb81;
	}

	.card-content {
		padding: 8px 16px;
	}

	img {
		margin: 0;
		padding: 0;
		width: 100%;
		border-radius: 8px 8px 0 0;
	}

	h2 {
		margin: 0 2px;
	}

	@media (max-width: 550px) {
		h2 {
			font-size: 18px;
		}
		.card {
			max-width: 150px;
		}
		.card-content > .card-content-main {
			font-size: 0px;
		}
	}
</style>
