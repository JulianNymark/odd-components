<script>
	import PlayingCard from '$lib/components/PlayingCard.svelte'

    // using TS
	// let my_deck: PlayingCard['$$prop_def']['card'][]

    // using JSDoc
    /** @type {import('$lib/components/PlayingCard.svelte').default['$$prop_def']['card'][]} */
    let my_deck

	my_deck = [
		{ suit: 'HEARTS', value: '10' },
		{ suit: 'SPADES', value: 'K' },
		{ suit: 'CLUBS', value: 'J' },
		{ suit: 'DIAMONDS', value: 'Q' }
	]
</script>

<h1>What's in this library?!</h1>

<h2>PlayingCard</h2>

{#each my_deck as card}
	<PlayingCard {card} />
{/each}
