<script lang="ts">
    import clickablePng from './assets/clickables/red.png'
    import { fly, fade } from 'svelte/transition';
    import {sussies, multiplier, susps} from './stores';
    function clickedSussy() {
        $sussies+=1*$multiplier;
    }
    setInterval(() => {$sussies+=$susps}, 1000)
</script>

<main>
    <img in:fly="{{ x: -200,duration: 1000, delay: 1000}}" src={clickablePng} alt="Click to get sussies!" on:click={clickedSussy} on:keypress={clickedSussy}>
        <p in:fade="{{duration: 3000}}">
            You have <br><span id="count"><b>{Math.floor($sussies)}</b></span><br> {$sussies === 1 ? 'sussy' : 'sussies'}!
        </p>
</main>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Rubik&display=swap');
    #count {
        font-size: 8vh
    }
    main {
        font-family: 'Rubik', sans-serif;
        font-size: 4vh;
        max-width: 50%;
        margin: 0 auto;
        padding: 2rem;
        text-align: center;
    }
    img {
        max-width: 100%;
        transition: linear 100ms;
    }
    img:hover {
        transform: scale(1.1);
    }
    img:active {
        transform: scale(0.9);
    }
</style>