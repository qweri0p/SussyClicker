<script lang='ts'>
    import BuyButton from './BuyButton.svelte';
    import { susps, sussies } from './stores';
    interface item {
        name:string
        description:string;
        suspersecond:number;
        price:number;
        amount:number;
        image:string;
    }
    let items:item[] = [
        {
        "name": "Vent",
        "description": "Use this to get called the sus.",
        "suspersecond": 1,
        "price": 15,
        "image": "./assets/purchasables/CHANGEME.png",
        "amount": 0
        },
        {
        "name": "Lights sabotage",
        "description": "Get sussy in the dark.",
        "suspersecond": 5,
        "price": 250,
        "image": "./assets/purchasables/CHANGEME.png",
        "amount": 0
        }

    ]
</script>
{#each items as thing}
    <BuyButton bind:thing/>
{/each}