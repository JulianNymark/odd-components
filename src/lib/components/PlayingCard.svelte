<script>
	/**
        @typedef {('SPADES' | 'HEARTS' | 'DIAMONDS' | 'CLUBS')} Suit
        @typedef {('2' | '3' | '4' | '5' | '6' | '7' | '8' | '9' | '10' | 'J' | 'Q' | 'K' | 'A')} Value
        @typedef {Object} CardInfo
        @property {Suit} suit
        @property {Value} value
    */

	/**
	 * @param {CardInfo['suit']} suit
	 */
	const renderSuit = (suit) => {
		switch (suit) {
			case 'CLUBS':
				return '♣'
			case 'HEARTS':
				return '♥'
			case 'SPADES':
				return '♠'
			case 'DIAMONDS':
				return '♦'
		}
	}

	/** @type CardInfo */
	export let card

	$: isRed = card.suit === 'DIAMONDS' || card.suit === 'HEARTS'
	$: color = isRed ? 'red' : 'black'
</script>

<div class="playing-card">
	<div class="card-content" style:color>
		{card.value}{renderSuit(card.suit)}
	</div>
</div>

<style>
	.playing-card {
		display: inline-block;
		margin: 0;
		padding: 0;
		border-radius: 6px;
		border: 1px solid black;
		box-shadow: 0px 4.8px 10px -5px rgba(0, 0, 0, 0.199),
			0px 10.1px 10.2px -5px rgba(0, 0, 0, 0.093);
		margin-right: 10px;
		font-size: large;
		width: 3em;
		height: 4em;
	}

	.playing-card > div {
		padding: 0;
		display: flex;
		flex-flow: column nowrap;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.card-content {
		flex: 0 1 auto;
		text-align: center;
		font-size: 1.6rem;
	}
</style>
