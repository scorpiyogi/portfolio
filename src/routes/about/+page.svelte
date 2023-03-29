<script lang="ts">
	import { onDestroy } from "svelte";

	const birthDate = new Date("2008-04-20");
	const today = new Date();

	function calculateAge(birthdate: Date) {
		const birthTime = new Date(birthdate).getTime();
		const nowTime = Date.now();
		const diffTime = nowTime - birthTime;
		const ageInMilliseconds = Math.abs(diffTime);
		const ageInYears = ageInMilliseconds / (1000 * 60 * 60 * 24 * 365);
		const ageWithDecimals = parseFloat(ageInYears.toFixed(9));
		return ageWithDecimals;
	}

	let age = calculateAge(birthDate);

	let interval = setInterval(() => {
		age = calculateAge(birthDate);
	}, 10);

	onDestroy(() => {
		clearInterval(interval);
	});
</script>

<svelte:head>
	<title>
		Gaurav Sohani - About Me
	</title>
</svelte:head>

<h1 class="text-2xl mb-4">About</h1>

<p>
	Greetings, dear reader! Allow me to introduce myself - I am Gaurav Sohani, a
	passionate full-stack developer hailing from the beautiful country of India.
	
 
	
</p>

<p>
	I am a Fullstack Engineer with a bachelor's in Electronics & Communications Engineering. After graduating I worked as a Digital Nomad in Raincode Technologies PVT LTD, where I developed world class, pixel perfect web and mobile applications for clients in US and UK. If you are looking for a NextJS or ReactJS then I'm the guy for you.
</p>

<p>
	In addition to programming, I have a number of other hobbies that keep me busy
	and engaged. I enjoy playing badminton, reading books, I also have a love for travel and exploration,
	always seeking out new places to discover and experience.
</p>

<p>
	Thank you for taking the time to read. I hope it has brought some
	inspiration and motivation to your day. Until next time, happy coding and stay
	curious!
</p>

<style>
     p{
        margin-bottom: 10px;
        line-height: 28px
     }
</style>