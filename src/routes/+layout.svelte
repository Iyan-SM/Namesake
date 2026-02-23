<script>
	import { onNavigate } from '$app/navigation';
	import { page } from '$app/stores';

	let { children } = $props();

	onNavigate((navigation) => {
		if (!document.startViewTransition) return;

		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});
</script>

<nav>
	<div class="bar home">
		{#if $page.url.pathname === '/'}
			<a href="/" class="deactivated">Home</a>
		{:else}
			<a href="/">Home</a>
		{/if}
	</div>

	<div class="bar code">
		{#if $page.url.pathname === '/code'}
			<a href="/code" class="deactivated">Code</a>
		{:else}
			<a href="/code">Code</a>
		{/if}
	</div>

	<div class="bar art">
		{#if $page.url.pathname === '/portfolio'}
			<a href="/portfolio" class="deactivated">3D Art</a>
		{:else}
			<a href="/portfolio">3D Art</a>
		{/if}
	</div>
</nav>

<div>
	{@render children()}
</div>

<style>
	nav {
		position: absolute;
		right: 5rem;
		font-family: 'Fugaz One', sans-serif;
		font-weight: 400;
		font-style: normal;
		font-size: x-large;
		writing-mode: vertical-rl;
		display: flex;
		flex-direction: column-reverse;
		align-items: left;
		justify-content: right;
		row-gap: 2rem;
		margin-right: 1.2rem;
		margin-bottom: 1.2rem;
		view-transition-name: header;
	}

	.deactivated {
		pointer-events: none;
		user-select: none;
	}

	.bar {
		border-radius: 0px 0px 10px 10px;
		text-align: right;
		align-content: center;
		width: 3rem;
		position: relative;
		top: 0;
	}

	.home {
		background-color: #e6bccd;
		box-shadow: 1px 1px 4px #c787a1;
		height: 10rem;
		transition: height ease 0.5s;
	}

	.home:not(.deactivated):hover {
		height: 10.4rem;
	}

	.home > a {
		padding-top: 5rem;
		padding-left: 1rem;
		padding-right: 1rem;
	}

	.code {
		background-color: #d295bf;
		box-shadow: 1px 1px 4px #94566e;
		height: 17rem;
		transition: height ease 0.5s;
	}
	.code:not(.deactivated):hover {
		height: 17.4rem;
	}

	.code > a {
		padding-top: 12rem;
		padding-left: 1rem;
		padding-right: 1rem;
	}


	.art {
		background-color: #7e52a0;
		box-shadow: 1px 1px 4px #2e1542;
		height: 24rem;
		transition: height ease 0.5s;
	}
	.art:not(.deactivated):hover {
		height: 24.4rem;
	}

	.art > a {
		padding-top: 18rem;
		padding-left: 1rem;
		padding-right: 1rem;
	}

	.bar > a {
		text-decoration: none;
		color: white;
		padding-bottom: 1rem;
	}

	@media screen and (max-width: 1160px) {
		nav {
			position: absolute;
			left: 0;
			font-family: 'Fugaz One', sans-serif;
			font-weight: 400;
			font-style: normal;
			font-size: x-large;
			writing-mode: horizontal-tb;
			display: flex;
			flex-direction: column;
			align-items: left;
			justify-content: center;
			row-gap: 2rem;
         margin-top: 1.2rem;
			margin-right: 1.2rem;
			view-transition-name: header;
		}
		.bar {
			border-radius: 0px 10px 10px 0px;
			text-align: right;
			align-content: center;
			height: 3rem;
			position: relative;
			top: 0;
		}
		.home {
			background-color: #e6bccd;
			box-shadow: 1px 1px 4px #c787a1;
			width: 87vw;
			transition: width ease 0.5s;
		}
		.home:not(.deactivated):hover {
			width: calc(87vw + 0.4rem);
         height: 3rem;
		}

		.home > a {
			padding-left: 65vw;
			padding-top: 1rem;
		}

		.code {
			background-color: #d295bf;
			box-shadow: 1px 1px 4px #94566e;
			width: 62vw;
			transition: width ease 0.5s;
		}
		.code:not(.deactivated):hover {
			width: calc(62vw + 0.4rem);
         	height: 3rem;
		}
		.code > a {
			padding-left: 26vw;
			padding-top: 1rem;
		}

		.art {
			background-color: #7e52a0;
			box-shadow: 1px 1px 4px #2e1542;
			width: 37vw;
			transition: width ease 0.5s;
		}
		.art:not(.deactivated):hover {
			width: calc(37vw + 0.4rem);
         	height: 3rem;
		}
		.art > a {
			padding-left: 18vw;
			padding-top: 1rem;
		}

      	.bar > a {
		text-decoration: none;
		color: white;
		padding-right: 1rem;
		}

	}

	/*Page Transitions*/
</style>
