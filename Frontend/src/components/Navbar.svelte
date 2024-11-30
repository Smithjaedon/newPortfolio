<script>
	let menuOpen = $state(false);

	const toggleMenu = () => {
		menuOpen = !menuOpen;
	};

	const closeMenu = () => {
		menuOpen = false;
	};
</script>

<header class="sticky top-0 max-h-16 w-screen bg-slate-800 px-4 text-slate-300">
	<nav class="flex w-full items-center justify-between p-4">
		<span>Jaedon Smith</span>
		<ul class="menu hidden list-none gap-4 md:flex" class:menu_open={menuOpen ? true : false}>
			<li>
				<a onclick={() => closeMenu()} class="uppercase hover:text-slate-600" href="#about">About</a
				>
			</li>
			<li>
				<a onclick={() => closeMenu()} class="uppercase hover:text-slate-600" href="#projects"
					>Projects</a
				>
			</li>
		</ul>
		<button class="text-3xl md:hidden" onclick={() => toggleMenu()}>☰</button>
	</nav>
</header>

<style>
	.menu_open {
		display: flex;
		flex-direction: column;
		position: absolute;
		top: 60px;
		left: 0;
		right: 0;
		background-color: #1e293b;
		z-index: 1000;
		text-align: center;
		padding-bottom: 10px;
	}

	/* ul {
		flex-direction: column;
		gap: 10px;
		padding: 10px;
		width: 100%;
		text-align: center;
	} */
</style>
