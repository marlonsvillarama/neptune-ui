<script>
    import Progress from "@/components/ui/progress/progress.svelte";

    let {
        progress = 0,
        title = 'Component',
        attention = [],
        status = 'ok',
        impact = 'low'
    } = $props();

    let statusText = $derived.by(() => {
        switch (status) {
            case 'critical': { return 'Critical' }
            case 'review': { return 'Needs Review' }
            default: { return 'Optimized' }
        }
    });

    let statusStyle = $derived.by(() => {
        switch (status) {
            case 'critical': { return 'red' }
            case 'review': { return 'amber' }
            case 'ok': { return 'green' }
        }
    });

    let impactStyle = $derived.by(() => {
        let output = ''
        switch (impact) {
            case 'high': { return 'red' }
            case 'medium': { return 'amber' }
            case 'low': { return 'green' }
            default: { output = 'default' }
        }
        return output
    });
</script>

<div class="grid gap-5 border-1 border-t-4 border-red rounded-sm pt-3 px-5 pb-5">
    <span class="text-lg font-semibold">Current</span>

    <!-- <div class="grid gap-1">
        <div class="flex items-center justify-between">
            <div class="text-sm text-{statusStyle}">{statusText}</div>
            <span class="text-sm font-semibold">{progress}%</span>
        </div>
        <Progress value={progress} class="bg-{statusStyle}" />
    </div> -->
</div>