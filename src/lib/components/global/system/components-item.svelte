<script>
    import {
        Check,
        CircleX,
        Info,
        Shield
    } from "@lucide/svelte";
    // import * as Progress from "@/components/ui/progress/index";
    import Badge from "@/components/ui/badge/badge.svelte";
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

<div class="grid grid-cols-[2fr_5fr_2fr] gap-12">
    <div class="grid gap-0">
        <span class="text-md font-semibold">{title}</span>
        {#if attention.length > 0}
            <span class="text-sm text-muted-foreground">{attention.length} item need{attention.length === 1 ? 's' : ''} attention</span>
        {/if}
    </div>
    <div class="grid gap-1">
        <div class="flex items-center justify-between">
            <div class="text-sm text-{statusStyle}">{statusText}</div>
            <span class="text-sm font-semibold">{progress}%</span>
        </div>
        <Progress value={progress} class="bg-{statusStyle}" />
    </div>
    <div class="flex items-center justify-center gap-4">
        <Badge variant={impactStyle} class="text-md font-bold">{impact.toUpperCase()}</Badge>
    </div>
</div>
