<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	
	import {AppShell} from '@skeletonlabs/skeleton';

	import Footer from '$lib/landing/Footer.svelte';
	import Header from '$lib/landing/Header.svelte';
	import Sidebar from '$lib/landing/Sidebar.svelte';

</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header"> <Header /> </svelte:fragment>
	<Sidebar />
	<slot />
	<svelte:fragment slot="footer"> <Footer /></svelte:fragment>
	
</AppShell>
