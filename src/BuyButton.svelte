<script lang="ts">
    import { sussies, susps, multiplier } from './stores'
    export let thing;
    function buy(item) {
        if ($sussies >= item.price) {
            $sussies -= item.price
            if (item.upgrade) {
                item.price = Math.floor( item.price*= 100 )
                $multiplier++
            } else {
                item.price = Math.floor( item.price*= 1.15 )
                $susps += item.suspersecond
            }
            item.amount++
            console.log(item)
            thing = thing
        }
    }
</script>
<div>
    <button on:click={() => {buy(thing)}}>{thing.name}</button>
    <br>
    <span>Price: {thing.price} sussies<br>You have {thing.amount} {thing.name}{thing.amount === 1 ? "":"s"}.</span><br>
</div>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');
    div {
        margin: 3em
    }
    button, span {
        font-family: 'Rubik', sans-serif;
        font-size: 4vh;
        transition: ease-in-out 200ms;
    }
    button:hover {
        transform: scale(1.1);
    }
    button:active {
        transform: scale(0.9);
    }
</style>