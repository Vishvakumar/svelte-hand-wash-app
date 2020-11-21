<script>
    import { createEventDispatcher } from 'svelte';
    import ProgressBar from './ProgressBar.svelte';

    const totalSec = 2;
    let secondsLeft = totalSec;
    let isRunning = false;

    $: progress = ((totalSec - secondsLeft) / totalSec) * 100;

    const dispatch = createEventDispatcher();

    function start() {
        isRunning = true;
        const timer = setInterval(() => {
            secondsLeft -= 1;
            if (secondsLeft == 0) {
                clearInterval(timer);
                isRunning = false;
                secondsLeft = totalSec;
                dispatch("end", "timer end");
            }
        },1000);        
    }


</script>

<style>
    button {
        border: 0 none;
        color: #fff;
        padding: 10px;
        text-decoration: none;
        display: inline-block;
        text-align: center;
        outline: none;
        flex: 1;
        cursor: pointer;
    }
    p { font-size: 20px; font-weight: bold; }
    .start { background-color: maroon; margin: 10px 0; width: 100%; }
    .start[disabled] {
        background-color: grey;
        cursor: not-allowed;
    }
</style>

<div bp="grid">
    <div bp="offset-5@md 4@md 12@sm">
        <p>Seconds Left: {secondsLeft}</p>
        <button disabled={isRunning} class="start" on:click="{start}">Start</button>
    </div>
</div>

<ProgressBar {progress} />