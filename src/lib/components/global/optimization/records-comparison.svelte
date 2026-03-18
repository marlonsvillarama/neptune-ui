<script>
    // import { FileText } from "@lucide/svelte";
    import RecordsComparisonChart from "./records-comparison-chart.svelte";
    import RecordsComparisonSummary from "./records-comparison-summary.svelte";
    let { badge } = $props();

    const chartData = [
        { metric: "Average Time", current: 15, neptune: 6 },
        { metric: "95th Percentile", current: 22, neptune: 8 }
    ];
</script>

<div class="grid gap-5 border rounded-sm pt-3 px-4 pb-5">
    <RecordsComparisonChart {badge} data={chartData} />
    <!-- <div class="flex items-center justify-between">
        <div class="flex items-center gap-2">
            <FileText size={24} class="text-muted-foreground" />
            <h2 class="text-sm text-muted-foreground uppercase">Sales Order</h2>
        </div>
    </div> -->
</div>