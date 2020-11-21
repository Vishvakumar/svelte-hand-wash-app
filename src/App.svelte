<script>
    import HowTo from './HowTo.svelte';
    import Timer from './Timer/Timer.svelte';
    let audio;
    function timerEnds() {
        //console.log(e);
        audio.play();
    }
    
</script>
<style>
    h1 { text-align: center; }
    /* .wrapper { max-width: 500px; margin: 0 auto;} */
    .links { text-align: center; font-size: 12px; }
</style>

<section>
    <div class="wrapper">
    <h1>Handwashing App</h1>

    <HowTo />
    <Timer on:end={timerEnds} />

    <!-- svelte-ignore a11y-media-has-caption -->
    <audio bind:this={audio}>
        <source src="sound-yeah.wav" >
    </audio>


    <div bp="grid " class="links">
        <div bp="offset-5@md 4@md">
        <a bp="6" href="https://www.who.int/gpsc/5may/How_To_HandWash_Poster.pdf">Picture Source</a>
        <a bp="6" href="https://freesound.org/people/metrostock99/sounds/345086/">Sound Source</a>
        </div>
    </div>

    </div>
</section>
