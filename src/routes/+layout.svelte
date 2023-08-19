<script lang="ts">
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';

	import { AppShell, AppBar, LightSwitch, Toast, Avatar } from '@skeletonlabs/skeleton';

	const menuItems = [
		{ inner: '🏓', href: '/pong' },
		{ inner: '💬', href: '/chans' },
		{ inner: '✉️', href: '/dms' },
		{ inner: '🤝', href: '/friends' }
	];
</script>

<!-- App Shell -->
<AppShell regionPage="w-full">
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar
			gridColumns="grid-cols-[auto_1fr_auto]"
			padding="px-2 py-2"
			slotLead=""
			slotDefault="place-self-center grid grid-cols-4"
			slotTrail="place-self-center"
		>
			<svelte:fragment slot="lead">
				<strong
					class="py-8 text-xs uppercase origin-center -rotate-45 md:text-lg md:rotate-0 lg:text-xl xl:text-2xl"
				>
					<a href="/">Transcendance</a>
				</strong>
			</svelte:fragment>
			{#each menuItems as menuItem}
				<a
					class="mx-4 mb-1 text-2xl font-semibold btn btn-sm variant-filled-success"
					href={menuItem.href}
				>
					{menuItem.inner}
				</a>
			{/each}
			<svelte:fragment slot="trail">
				<button class="mr-1 text-xs font-semibold btn btn-sm variant-filled-secondary">
					Log out
				</button>
				<a href="/myprofile" class="flex ml-1 chip variant-ghost">
					<Avatar src="https://i.pravatar.cc/?u=Jane" class="w-8 h-8" rounded="rounded-full" />
					<div>Jane</div>
				</a>
				<LightSwitch />
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
	<Toast />
</AppShell>
