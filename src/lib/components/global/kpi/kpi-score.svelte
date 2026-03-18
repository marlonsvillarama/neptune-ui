<script>
    import * as Card from '@/components/ui/card/index';
    let {
        score = 0
    } = $props();
</script>

<!-- <div class="opt-score border rounded-xl shadow-sm h-[12rem] text-center flex flex-col gap-3 pt-7"> -->
<Card.Root class="">
    <Card.Content class="h-[9rem] text-center flex flex-col gap-3 py-2">
        <h1 class="text-7xl font-bold text-primary/80">{score}</h1>
        <div class="flex flex-col gap-1">
            <span class="text-md font-semibold">Optimization Score</span>
            <span class="text-md font-normal">Target: 100</span>
        </div>
    </Card.Content>
</Card.Root>
<!-- </div> -->
