<script lang="ts">
	import type { Movie } from '$lib/schemas'

	export let showtimes: [string, Movie['showtimes']][]
</script>

<div>
	<div class="space-y-4">
		{#each showtimes as [cinema, times] (cinema)}
			<div>
				<div class="mb-3 font-medium text-neutral-200">{cinema}</div>
				<div class="inline-flex flex-wrap gap-3">
					{#each times as { time, purchase_url } (purchase_url)}
						<a
							class="relative group tabular-nums px-2.5 py-1 text-base rounded-md bg-gradient-to-br from-neutral-800 to-neutral-900 text-neutral-300 hover:bg-neutral-700 hover:text-white"
							href={purchase_url}
						>
							<span
								class="absolute inset-0 rounded-md opacity-5 shadow-[inset_0_1px_1px_white] transition-opacity group-hover:opacity-10"
							/>
							{new Date(time).toLocaleTimeString('is-IS', {
								timeStyle: 'short',
								hour12: false
							})}
						</a>
					{/each}
				</div>
			</div>
		{/each}
	</div>
</div>
