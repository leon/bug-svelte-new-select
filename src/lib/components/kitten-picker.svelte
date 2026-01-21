<script lang="ts">
	import Select from './select.svelte';

	interface Props {
		value: {
			name: string;
			image: string;
		};
	}
	let { value = $bindable() }: Props = $props();

	let kittens = [
		{
			name: 'Neo',
			image: 'https://placecats.com/neo/300/200'
		},
		{
			name: 'Millie',
			image: 'https://placecats.com/millie/300/200'
		},
		{
			name: 'Bella',
			image: 'https://placecats.com/bella/300/200'
		},
		{
			name: 'Poppy',
			image: 'https://placecats.com/poppy/300/200'
		}
	];
</script>

<Select bind:value>
	<button>
		<selectedcontent class="flex items-center gap-2"></selectedcontent>
	</button>
	{#each kittens as kitten (kitten.name)}
		<option class="flex gap-2" value={kitten}>
			<img class="block h-12 w-12 object-contain" alt="" src={kitten.image} />
			{kitten.name}
		</option>
	{/each}
</Select>
