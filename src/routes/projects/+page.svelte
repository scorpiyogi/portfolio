<script>
	const projects = [
		{
			name: "Laboratory",
			description: "Experiments based on P5js library",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/laboratory",
		},
		{
			name: "Music Player",
			description: "An app like Spotify built with React, Next.js, PostgreSQL, and Prisma would be a modern music streaming service offering a seamless user experience",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/Music-Player",
		},
		{
			name: "DAO-starter",
			description: "A DAO membership page where user can connect their wallet, Mint the NFTs, and can see who is part of DAO and how many tokens they own along with some proposals things. Also, the members can use governance tokens to vote on proposals.",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/DAO-starter",
		},
		{
			name: "Discord-bot",
			description: "A Discord bot is a program that interacts with the popular online chat platform, Discord, to perform various automated tasks. It can be programmed to do things like respond to user commands, provide information and moderate conversations",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/bots/tree/master/2",
		},
		{
			name: "Domain-starter",
			description: "A Domain Name Service based on Polygon Blockchain, which is a lot like ENS(Ethereum name service). Users can sell a domain on the blockchain, anyone can set data or record for their domain. I've got mine as Yogi Name Service and the domain name as scorpi.yogi . You can mint your domain by writing its name and power. and by paying some gas fee. ",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/domain-starter",
		},
		{
			name: "opensea-blockchain-clone",
			description: "An app like OpenSea  would be a decentralized marketplace for buying and selling digital assets, such as non-fungible tokens (NFTs) and other unique items.The app would be similar to OpenSea, which is one of the largest marketplaces for NFTs and other digital assets. ",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/opensea-blockchain-clone",
		},
		{
			name: "WhatsApp Clone",
			description: "WhatsaAn app like WhatsApp Clone would be a messaging platform that allows users to send and receive text messages, voice messages, images, and videos over the internet.",
			roles: ["Creator"],
			link: "https://github.com/scorpiyogi/Whatsapp-clone",
		},
	];
</script>

<svelte:head>
	<title>Gaurav Sohani - Projects I've worked on</title>
</svelte:head>

<h1 class="text-2xl mb-4">Projects</h1>

<div class="grid md:grid-cols-3 gap-3 sm:grid-cols-2">
	{#each projects as project}
		<div
			class="col-span-1 bg-base-200 p-6 rounded hover:bg-base-300 transition-all"
		>
			<h1 class="text-xl">{project.name}</h1>
			<p class="my-2 text-sm">{project.description}</p>

			{#each project.roles as role}
				<button class="btn btn-xs btn-outline"> {role} </button>
			{/each}

			<br />

			<a href={project.link} target="_blank" class="link mt-2 block text-sm"
				>{project.link}
			</a>
		</div>
	{/each}
</div>
