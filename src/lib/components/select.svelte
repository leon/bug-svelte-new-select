<script lang="ts">
	import type { Snippet } from 'svelte';
	import type { HTMLSelectAttributes } from 'svelte/elements';

	interface Props extends HTMLSelectAttributes {
		children: Snippet;
	}
	let { value = $bindable(), children, class: className, ...props }: Props = $props();
</script>

<select
	class={['flex items-center rounded-sm bg-neutral-200 px-4', className]}
	{...props}
	bind:value
>
	{@render children()}
</select>

<style>
	select,
	::picker(select) {
		appearance: base-select;
	}
</style>
