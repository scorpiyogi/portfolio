<script>
	import Icon from "@iconify/svelte";
	import { onDestroy } from "svelte";
	import { fly } from "svelte/transition";
	import SpotifyStatus from "./SpotifyStatus.svelte";

	const socialArr = [
		{ name: "GitHub", icon: "uiw:github", link: "https://github.com/scorpiyogi" },
		{
			name: "Twitter",
			icon: "akar-icons:twitter-fill",
			link: "https://twitter.com/scorpiyogi1",
		},
		 
		{
			name: "LinkedIn",
			icon: "akar-icons:linkedin-fill",
			link: "https://www.linkedin.com/in/gaurav-sohani/",
		},
		 
		 
	];

	const quotes = [
		{
			text: "Gaurav is an incredibly talented developer. I've had the pleasure of collaborating with him on several projects, and I'm always impressed by his knowledge and skillset. I have no doubt he'll continue to excel in his future endeavours.",
			name: "Ayush Sharma",
			link: "https://github.com/a-y-u-s-h",
			who: "Co-worker",
		},
		{
			text: "Gaurav is one of the best developers I have met and he has very impressive and creative skills. I wish him all the best",
			name: "Shreyansh Sharma",
			link: "https://www.linkedin.com/in/shreyansh-sharma-3386621b2/",
			who: "Co-worker",
		},
	];

	let activeQuote = 0;

	const interval = setInterval(() => {
		activeQuote = activeQuote === quotes.length - 1 ? 0 : activeQuote + 1;
	}, quotes[activeQuote].text.length * 50 + 1000);

	onDestroy(() => {
		clearInterval(interval);
	});
</script>

<svelte:head>
	<title>Gaurav Sohani - Fullstack Engineer</title>
</svelte:head>

<div class="flex">
	<div class="flex-1">
		<div class="avatar">
			<div class="w-36 mask mask-squircle">
				<img
					src="avatar.png"
					alt="avatar"
				/>
			</div>
		</div>

		<h1 class="text-4xl mt-2 font-semibold">Gaurav Sohani</h1>
		<p class="mt-2 mb-6">Fullstack Engineer</p>
	</div>

	<div class="relative">
		<SpotifyStatus />
	</div>
</div>

<div class="max-h-max overflow-hidden">
	{#each quotes as quote, i}
		{#if i == activeQuote}
			<div
				class="bg-base-200 rounded mb-4 p-4 hover:bg-base-300 transition-all"
			>
				<blockquote class="blockquote">
					<p class="mb-2 italic">"{quote.text}"</p>
					<a href={quote.link} target="_blank" class="text-sm"
						>{quote.name} - {quote.who}</a
					>
				</blockquote>
			</div>
		{/if}
	{/each}
</div>

<br />

{#each socialArr as social}
	<div class="tooltip tooltip-bottom mr-2" data-tip={social.name}>
		<a href={social.link} target="_blank" class="btn btn-circle">
			<Icon icon={social.icon} class="inline text-2xl" />
		</a>
	</div>
{/each}

<br />

<p class="mt-4">
	Discord: <span class="text-gray-300">Gaurav Sohani#2216</span>
</p>

<p class="mt-2">
	Email: {#each "sohani.codes@gmail.com ,".split(`,`) as item}
		<a href={`mailto:${item}`} class="text-gray-300">{item}</a>{@html `&nbsp;`}
	{/each}
</p>

 

<p class="mt-2">
	Ethereum: <span class="text-gray-300">Gaurav.eth</span>
</p>

 
