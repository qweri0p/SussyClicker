<script lang="ts">
    import { sussies, susps } from './stores'
    export let thing;
    function buy(item) {
        if ($sussies >= item.price) {
            $sussies -= item.price
            item.price = Math.floor( item.price*= 1.15 )
            item.amount++
            $susps += item.suspersecond
            console.log(item)
            thing = thing
        }
    }
</script>

<main>
<button on:click={() => {buy(thing)}}>{thing.name}</button>
<br>
<span>Price: {thing.price} sussies<br>You have {thing.amount} {thing.name}{thing.amount === 1 ? "":"s"}.</span><br>
</main>


<style>
    main {
        margin: 3em
    }
    @import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');
    button, span {
        font-family: 'Rubik', sans-serif;
        font-size: 6vh;
        transition: ease-in-out 200ms;
    }
    button:hover {
        transform: scale(1.1);
    }
    button:active {
        transform: scale(0.9);
    }
</style>