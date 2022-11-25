<script lang='ts'>
    import BuyButton from './BuyButton.svelte';
    import { susps, sussies } from './stores';
    interface item {
        name:string
        description:string;
        suspersecond?:number;
        price:number;
        amount:number;
        image:string;
        upgrade:boolean;
    }
    let items:item[] = [
        {
            "name": "More impostors",
            "description": "It was a multi kill!",
            "image": "./assets/purchasables/CHANGEME.png",
            "amount": 0,
            "upgrade": true,
            "price": 25
        },
        {
            "name": "Vent",
            "description": "Use this to get called the sus.",
            "suspersecond": 1,
            "price": 50,
            "image": "./assets/purchasables/CHANGEME.png",
            "amount": 0,
            "upgrade": false
        },
        {
            "name": "Lights sabotage",
            "description": "Get sussy in the dark.",
            "suspersecond": 5,
            "price": 500,
            "image": "./assets/purchasables/CHANGEME.png",
            "amount": 0,
            "upgrade": false
        }

    ]
</script>
{#each items as thing}
    <BuyButton bind:thing/>
{/each}