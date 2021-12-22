<script type="ts">
	import SkeletonLoader from '$lib/components/skeleton-loader.svelte';
	import sleep from 'await-sleep';
	import VideoPlayer from 'svelte-video-player';

	const loadParagraph = async () => {
		await sleep(1);
	};

	const dummyLoader = loadParagraph();
</script>

<section>
	{#await dummyLoader}
		<SkeletonLoader width={100} count={2} />
	{:then _}
		<div>
			<h2>Hello Temporal!</h2>
			<p>Over the time I've been at Temporal I've grown so much as a developer.</p>
			<p>
				Here a few things I've worked on while at Temporal and also some projects I have done on the
				side that I wouldn't have learned without Temporal.
			</p>
		</div>
		<div class="cards">
			<div class="card card-1">
				<h2>Triagery</h2>
				<div class="card__title">
					<p>
						My first months at Temporal I worked on a internal tool called Triagery, it was a
						issue/task aggregation tool that moved Github issues to Notion.
					</p>
					<p>
						Triagery was my first introduction to creating a design docs and creating user stories.
					</p>
				</div>
				<p class="card__apply">
					<a class="card__link" href="https://github.com/temporalio/triagery">Github </a>
				</p>
			</div>
			<div class="card card-2">
				<h2>UI</h2>
				<div class="card__title">
					<p>
						My first months at Temporal I worked on a internal tool called Triagery, it was a
						issue/task aggregation tool that moved Github issues to Notion.
					</p>
					<p>
						Triagery was my first introduction to creating a design docs and creating user stories.
					</p>
				</div>
				<p class="card__apply">
					<a class="card__link" href="https://github.com/temporalio/ui">Github </a>
				</p>
			</div>
			<div class="card card-3">
				<h2>Ghost Town Goblins</h2>
				<div class="card__title">
					<p>
						Ghost Town Goblins was a weekend project that I worked on, it was my first project using
						svelte.
					</p>
				</div>
				<p class="card__apply">
					<a class="card__link" href="https://www.goblinsgame.com/">Website </a>
				</p>
			</div>
		</div>
	{/await}
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		margin: 1rem;
	}

	.cards {
		display: flex;
		justify-content: space-between;
		overflow-x: auto;
	}

	.card {
		margin: 20px;
		padding: 20px;
		width: 500px;
		min-height: 200px;
		display: grid;
		grid-template-rows: 20px 50px 1fr 50px;
		border-radius: 10px;
		box-shadow: 0px 6px 10px rgba(0, 0, 0, 0.25);
		transition: all 0.2s;
		color: #fff;
	}

	.card:hover {
		box-shadow: 0px 6px 10px rgba(0, 0, 0, 0.4);
		transform: scale(1.01);
	}

	.card__link {
		position: relative;
		text-decoration: none;
		color: rgba(255, 255, 255, 0.9);
	}

	.card__link::after {
		position: absolute;
		top: 25px;
		left: 0;
		content: '';
		width: 0%;
		height: 3px;
		background-color: rgba(255, 255, 255, 0.6);
		transition: all 0.5s;
	}

	.card__link:hover::after {
		width: 100%;
	}

	.card__title {
		grid-row: 3/4;
		font-weight: 400;
		color: #ffffff;
	}

	.card__apply {
		grid-row: 4/5;
		align-self: center;
	}

	.card-1 {
		background-color: #4158d0;
		background-image: linear-gradient(43deg, #4158d0 0%, #c850c0 46%, #ffcc70 100%);
	}

	.card-2 {
		background-color: #0093e9;
		background-image: linear-gradient(160deg, #0093e9 0%, #80d0c7 100%);
	}

	.card-3 {
		background-image: linear-gradient(135deg, #e2b0ff 10%, #9f44d3 100%);
	}
</style>
