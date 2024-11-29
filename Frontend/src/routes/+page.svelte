<script>
	import Navbar from '../components/Navbar.svelte';
	import ProjectCard from '../components/ProjectCard.svelte';

	let projects = [
		{
			name: 'Portfolio',
			description: 'A portfolio website built using SvelteKit and TailwindCSS.',
			link: 'https://github.com/SmithJaedon/portfolio',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript']
		},
		{
			name: 'Todo App',
			description:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Non provident ex modi, praesentium laudantium iste veritatis dolore odio molestiae temporibus debitis ipsum nobis, ab suscipit ratione. Molestiae dicta commodi tempore? Ducimus, nesciunt velit! Voluptates omnis sed harum consequuntur illo temporibus aspernatur atque eveniet tempora. Blanditiis corporis, id ducimus molestias eius molestiae est perferendis beatae eaque ex modi obcaecati rerum fugiat!',
			link: 'https://github.com/SmithJaedon/todo-app',
			badges: ['SvelteKit', 'TailwindCSS', 'JavaScript']
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

<main class="text-slate-300 snap-y snap-mandatory mx-auto mt-14">
	<section id="about" class="mx-auto">
		<div class="flex justify-center items-center h-[80vh]">
			<div>
				<div class="text-center">
					<h1 class="text-6xl">Jaedon Smith</h1>
					<p class="bg-slate-500 px-4 py-2 inline-block rounded-xl mt-4">Software Engineer</p>
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
		<div class="flex justify-center items-center h-[80vh]">
			<div class="text-center">
				<h2 class="text-6xl text-slate-300">Projects</h2>
				<div class="container mx-auto grid grid-cols-1 gap-4 mt-10">
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
		class="fixed bottom-4 right-4 bg-slate-800 hover:bg-slate-600 text-slate-300 px-4 py-2 rounded-md"
		on:click={scrollToTop}>Back to top</button
	>
</main>
