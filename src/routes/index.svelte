<script context="module">
	
	export function preload({ params, query }) {
		return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
			return { posts };
		});
	}
</script>

<script>
	import Post from '../components/Post.svelte'
	export let posts;
</script>

<style>
	.Home {
		padding: 2em 0;
		min-height: calc(100vh - 251px);
	}
	.Posts {
		display: grid;
		justify-content: space-between;
		grid-gap: 15px;
		grid-template-columns: 1fr 1fr 1fr;
	}

	@media screen and (max-width: 768px) {
		.Posts {
			grid-template-columns: 1fr; 
		}
	}

	@media screen and (max-width: 993px) {
		.Home {
			padding: 2em 1em;
		}
	}
	@media (min-width: 769px) and (max-width: 993px) {
		.Posts {
			grid-template-columns: 1fr 1fr;
		}
	}
	

</style>

<svelte:head>
	<!-- Primary Meta Tags -->
	<title>📰 Dartiles Dev | 💡 Angular, React, Svelte, Vue, Javascript</title>
	<meta name="title" content="📰 Dartiles Dev | 💡 Angular, React, Svelte, Vue, Javascript">
	<meta name="description" content="Refuerza tus conocimientos en todas las librerías y frameworks de Javascript, descubre trucos y consejos para ser un mejor programador frontend 💖">
	<meta name="keywords" content="javascript, react, svelte, angular, nodejs, nestjs, tutoriales, hooks de react, trucos de svelte, react hooks, redux, jsx">

	<!-- Open Graph / Facebook -->
	<meta property="og:type" content="website">
	<meta property="og:url" content="https://dartiles.dev/">
	<meta property="og:title" content="📰 Dartiles Dev | 💡 Angular, React, Svelte, Vue, Javascript">
	<meta property="og:description" content="Refuerza tus conocimientos en todas las librerías y frameworks de Javascript, descubre trucos y consejos para ser un mejor programador frontend 💖">
	<meta property="og:image" content="https://dartiles.dev/media/main/main-image.jpg">
	<meta property="og:locale" content="es_ES">

	<!-- Twitter -->
	<meta name="twitter:card" content="summary_large_image">
	<meta name="twitter:site" content="@dartilesm" />
	<meta name="twitter:creator" content="@dartilesm" />
	<meta name="twitter:url" content="https://dartiles.dev/">
	<meta name="twitter:title" content="📰 Dartiles Dev | 💡 Angular, React, Svelte, Vue, Javascript">
	<meta name="twitter:description" content="Refuerza tus conocimientos en todas las librerías y frameworks de Javascript, descubre trucos y consejos para ser un mejor programador frontend 💖">
	<meta name="twitter:image" content="https://dartiles.dev/media/main/main-image.jpg">
</svelte:head>

<div class="Home">
	<div class="Posts">
		{#each posts as post}
			<Post {post} />
		{/each}
	</div>
</div>