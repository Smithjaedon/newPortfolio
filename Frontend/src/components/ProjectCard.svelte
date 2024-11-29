<script>
	export let project_name;
	export let project_description;
	export let project_link;
	export let project_badges;

	const openLink = () => {
		window.open(project_link, '_blank');
	};
</script>

<div
	class="bg-slate-800 p-4 h-full border-[2px] border-slate-500 rounded-lg hover:border-slate-300 group/link max-w-prose"
>
	<div class="flex justify-between items-center">
		<h3>
			<a
				href={project_link}
				target="_blank"
				class="group-hover/link:underline group-hover/link:text-slate-300">{project_name}</a
			>
		</h3>
		<button class="" aria-label="Link to project" on:click={openLink}
			><svg
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 20 20"
				fill="currentColor"
				class="inline-block h-4 w-4 shrink-0 transition-transform group-hover/link:-translate-y-1 group-hover/link:translate-x-1 group-focus-visible/link:-translate-y-1 group-focus-visible/link:translate-x-1 motion-reduce:transition-none ml-1 translate-y-px"
				aria-hidden="true"
				><path
					fill-rule="evenodd"
					d="M5.22 14.78a.75.75 0 001.06 0l7.22-7.22v5.69a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75h-7.5a.75.75 0 000 1.5h5.69l-7.22 7.22a.75.75 0 000 1.06z"
					clip-rule="evenodd"
				></path></svg
			></button
		>
	</div>

	<p class="text-left">{project_description}</p>
	<div class="container mx-auto flex gap-2 mt-4">
		{#if project_badges}
			{#each project_badges as badge}
				<span class="bg-slate-500 px-2 py-1 rounded-md text-sm">{badge}</span>
			{/each}
		{/if}
	</div>
</div>
