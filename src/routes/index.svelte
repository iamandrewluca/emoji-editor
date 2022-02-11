<script lang="ts">
	const data = [
		["🟥", "🟩", "🟦", "🟥", "🟩", "🟦"],
		["🟥", "🟩", "🟦", "🟥", "🟩", "🟦"],
		["🟥", "🟩", "🟦", "🟥", "🟩", "🟦"],
		["🟥", "🟩", "🟦", "🟥", "🟩", "🟦"],
		["🟥", "🟩", "🟦", "🟥", "🟩", "🟦"],
		["🟥", "🟩", "🟦", "🟥", "🟩", "🟦"],
	];
</script>

<main class="container mx-auto max-w-xl p-4">
	{#each data as row}
		<div class="text-center">
			{#each row as column}
				<button class="text-5xl">
					{column}
				</button>
			{/each}
		</div>
	{/each}
</main>
