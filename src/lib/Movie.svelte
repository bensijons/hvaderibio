<script lang="ts">
	import type { Movie } from '$lib/schemas'

	export let movie: Movie
</script>

<button on:click|preventDefault>
	<img
		src={`posters/${movie.images[0].path}`}
		title={movie.title}
		alt={movie.title}
		class="object-fill aspect-[2/3] rounded-lg shadow-2xl sm:w-[min(100%,360px)] sm:hover:scale-105 sm:hover:z-50 sm:transition-all"
	/>
</button>
