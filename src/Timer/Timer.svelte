<script>
    import ProgressBar from './ProgressBar.svelte';
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
</style>

<div bp="grid">
    <div bp="offset-5@md 4@md 12@sm">
        <p>Seconds Left: </p>
        <button class="start">Start</button>
    </div>
</div>

<ProgressBar/>