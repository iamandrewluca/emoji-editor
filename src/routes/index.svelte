<script lang="ts">
	const items = [
		"🟩",
		"🟥",
		"🟦",
		"⬜️",
		"🟪",
		"🟨",
		"🟫",
		"⬛",
		"🔴",
		"🟣",
		"⚪️",
		"🟠",
		"⚫️",
		"🟡",
		"🟢",
	];

	let selectedItem = items[0];

	let row = 7;
	let column = 18;

	$: data = [...Array(row)].map(() =>
		[...Array(column)].map(() => selectedItem),
	);
</script>

<main class="container mx-auto max-w-xl p-4">
	<div class="flex gap-px">
		{#each items as item}
			<button
				class="leading-none p-1 bg-red-100 border-b-2"
				class:border-transparent={item !== selectedItem}
				class:border-red-500={item === selectedItem}
				on:click={() => (selectedItem = item)}
			>
				{item}
			</button>
		{/each}
	</div>

	<div class="py-1 border-t border-b mt-3 mb-1">
		<button on:click={() => row++}>+ Row</button>
		<button on:click={() => row--}>- Row</button>
		<button on:click={() => column++}>+ Column</button>
		<button on:click={() => column--}>- Column</button>
	</div>

	<div
		class="inline-grid gap-px place-content-center bg-red-500 p-px"
		style:grid-template-rows="repeat({row}, minmax(0, 1fr))"
		style:grid-template-columns="repeat({column}, minmax(0, 1fr))"
	>
		{#each data as row}
			{#each row as column}
				<button
					class="bg-red-50 text-red-500 aspect-square leading-none text-xl p-1"
				>
					{column}
				</button>
			{/each}
		{/each}
	</div>
</main>
