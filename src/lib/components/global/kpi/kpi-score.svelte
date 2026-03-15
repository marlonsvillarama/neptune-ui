<script>
    let {
        score = 0
    } = $props();
</script>

<div class="opt-score h-[12rem] text-center flex flex-col gap-3 pt-7">
    <h1 class="text-7xl font-bold">{score}</h1>
    <div class="flex flex-col gap-1">
        <span class="text-md font-semibold">Optimization Score</span>
        <span class="text-md font-semibold text-muted-foreground">Target: 100</span>
    </div>
</div>
