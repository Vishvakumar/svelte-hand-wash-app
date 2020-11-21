<script>
    export let progress = 0;
</script>

<style>
    .progress-container { border: 1px solid gray; margin: 10px 0; }
    .progress-bar { height: 30px; background-color: greenyellow; }
    .sr-only { display: none;}
</style>

<div bp="grid">
    <div bp="offset-5@md 4@md 12@sm" class="progress-container">
        <div class="progress-bar" style="width: {progress}%">
            <span class="sr-only">%{progress}</span>
        </div>
    </div>
</div>