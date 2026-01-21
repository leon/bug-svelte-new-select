<script lang="ts">
	import KittenPicker from '$lib/components/kitten-picker.svelte';

	let kitten: any = $state();
</script>

<div class="grid h-screen w-full place-content-center gap-4">
	<div class="grid gap-2">
		<KittenPicker bind:value={kitten} />
		{kitten?.name}
	</div>
</div>
