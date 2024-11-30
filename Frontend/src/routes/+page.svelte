<script>
	import Navbar from '../components/Navbar.svelte';
	import ProjectCard from '../components/ProjectCard.svelte';

	let projects = [
		{
			name: 'Portfolio Webiste',
			description:
				'A portfolio website built using SvelteKit and TailwindCSS. You are currently viewing it!',
			link: 'https://port24-wheat.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		},
		{
			name: 'Ping Pong Game',
			description:
				'A simple ping pong game built using HTML, CSS, and JavaScript in SvelteKit with TailwindCSS. The game features a two-player mode.',
			link: 'https://pong-v2-six.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		},
		{
			name: 'TicTacToe Game',
			description:
				'A simple TicTacToe game built using HTML, CSS, and JavaScript in SvelteKit with TailwindCSS. The game features a two-player mode and a color theme toggle.',
			link: 'https://tictactoe-v2.vercel.app/',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript', 'Vite', 'Vercel']
		}
	];

	// Function to scroll to the top of the page
	const scrollToTop = () => {
		const c = document.documentElement.scrollTop || document.body.scrollTop;
		if (c > 0) {
			window.requestAnimationFrame(scrollToTop);
			window.scrollTo(0, c - c / 8);
		}
	};
</script>

<svelte:head>
	<title>Jaedon Smith</title>
	<style>
		body {
			background: #374151;
		}
	</style>
</svelte:head>

<Navbar />

<main class="mx-auto mt-14 snap-y snap-mandatory text-slate-300">
	<section id="about" class="mx-auto">
		<div class="flex h-[80vh] items-center justify-center">
			<div>
				<div class="text-center">
					<h1 class="text-6xl">Jaedon Smith</h1>
					<p class="mt-4 inline-block rounded-xl bg-slate-500 px-4 py-2">Software Engineer</p>
					<p class="mt-8 max-w-prose">
						Hi! I’m Jaedon Smith, a Computer Science student with a passion for learning and solving
						problems. I love exploring new technologies and building projects that challenge me.
						Whether it’s learning JavaScript through online courses or experimenting with new coding
						concepts for an assignment, I’m always eager to grow my skills. I’m a quick learner,
						adaptable, and thrive in dynamic environments.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section id="projects" class="mx-auto mt-14">
		<div class="flex h-[80vh] items-center justify-center">
			<div class="text-center">
				<h2 class="text-6xl text-slate-300">Projects</h2>
				<div class="container mx-auto mt-10 grid grid-cols-1 gap-4">
					{#each projects as project}
						<ProjectCard
							project_name={project.name}
							project_description={project.description}
							project_link={project.link}
							project_badges={project.badges}
						/>
					{/each}
				</div>
			</div>
		</div>
	</section>
	<button
		class="fixed bottom-4 right-4 rounded-md bg-slate-800 px-4 py-2 text-slate-300 hover:bg-slate-600"
		on:click={scrollToTop}>Back to top</button
	>
</main>
