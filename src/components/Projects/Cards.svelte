<script>
	export let title = '';
	export let text = '';
	import { fade } from "svelte/transition";
	import { onMount } from "svelte";

  let card;
  let observer;

  onMount(() => {
    observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add("fade-in");
          observer.unobserve(entry.target);
        }
      });
    });

    observer.observe(card);

    return () => {
      observer.disconnect();
    };
  });
</script>

<div class="container" bind:this={card}>
<div class="card" transition:fade>
	<div class="img-container">
		<slot name="img1" />
	</div>
	<div class="text-container">
		<div class="title">
			<slot name="title">
				<h3>{title}</h3>
			</slot>
		</div>
		<div class="text">
			<slot name="text">
				<p>{text}</p>
			</slot>
		</div>
	</div>
</div>
</div>
<style>
	.text-container {
		display: flex;
		justify-content: flex-start;
		align-items: flex-start;
		text-align: left;
	}

	.img-container {
		width: 100px;
		height: 100px;
	}

	.card {
		padding: 1.5rem;
		height: 400px;
		width: 300px;
		background-color: black;
		border: 2px solid white;
		border-radius: 25px;
		display: flex;
		justify-content: center;
		cursor: pointer;
		transform: translateY(-10px);
		flex-direction: column;
		gap: 1rem;
	}

	.card:hover {
		box-shadow: 10px 0px 20px -5px #a5bdfc, -10px 0px 20px -5px #c547fa, 0px 10px 20px -5px #3f75fc;
	}
</style>
