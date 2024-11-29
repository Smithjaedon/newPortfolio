<script>
	export let project_name;
	export let project_description;
	export let project_link;
	export let project_badges;

	const openLink = () => {
		window.open(project_link, '_blank');
	};
</script>

<div class="bg-slate-800 p-4 h-full border-slate-500 rounded-lg">
	<h3>{project_name}</h3>
	<p>{project_description}</p>
	{#if project_badges}
		{#each project_badges as badge}
			<span class="bg-slate-500 px-2 py-1 rounded-md text-sm">{badge}</span>
		{/each}
	{/if}
</div>
