# odd-components

Svelte components you might occasionally want!

# Install

```bash
npm i odd-components
```

# Components

## PlayingCard

![text](https://raw.githubusercontent.com/JulianNymark/odd-components/main/README/playingcard.png)

- no custom icons, uses utf-8

### Svelte
```html
<script>
    import { PlayingCard } from 'odd-components'

    // using TS
    // let my_deck: PlayingCard['$$prop_def']['card'][]

    /** @type {PlayingCard['$$prop_def']['card'][]} */
    let my_deck

    my_deck = [
        { suit: 'HEARTS', value: '10' },
        { suit: 'SPADES', value: 'K' },
        { suit: 'CLUBS', value: 'J' },
        { suit: 'DIAMONDS', value: 'Q' }
    ]
</script>

{#each my_deck as card}
	<PlayingCard {card} />
{/each}

```
