<script>
    import { FileText } from "@lucide/svelte";
    import { scaleBand } from "d3-scale";
    import { BarChart } from "layerchart";
    import * as Chart from "@/components/ui/chart/index";
    import * as Select from "@/components/ui/select/index";
    import Badge from "@/components/ui/badge/badge.svelte";
    import { cubicInOut } from "svelte/easing";
    import { nonpassive } from "svelte/legacy";

    let {
        badge,
        data
    } = $props();

    const chartConfig = {
        current: { label: 'Current', color: "var(--red)" },
        neptune: { label: 'Neptune', color: "var(--green)" },
    };

    let context = $state();
</script>

<div class="grid gap-5">
    <div class="flex items-center justify-between">
        <div class="flex items-center gap-2">
            <FileText size={24} class="text-muted-foreground" />
            <h2 class="text-sm font-semibold">Sales Order Performance</h2>
        </div>
        <Select.Root>
            <Select.Trigger class="">
                <!-- <Badge variant="default text-xs"> -->
                    <span class="text-xs uppercase">{badge}</span>
                <!-- </Badge> -->
            </Select.Trigger>
        </Select.Root>
    </div>
    <Chart.Container config={chartConfig}>
        <BarChart
            bind:context
            {data}
            x="metric"
            series={[
                { key: 'current', label: 'Current', color: chartConfig.current.color },
                { key: 'neptune', label: 'With Neptune', color: chartConfig.neptune.color },
            ]}
            x1Scale={scaleBand().paddingInner(0.1)}
            seriesLayout="group"
            props={{
                bars: {
                    stroke: "none",
                    strokeWidth: 0,
                    rounded: "top",
                    initialY: context?.height,
                    initialHeight: 0,
                    motion: {
                        y: { type: "tween", duration: 500, easing: cubicInOut },
                        height: { type: "tween", duration: 500, easing: cubicInOut },
                    }
                },
                xAxis: { format: (d) => d },
                yAxis: { format: 'metric' }
            }}
            legend
        >
            <!-- axis="x" -->
            <!-- xScale={scaleBand().padding(0.25)} -->
            <!-- rule={false} -->
                <!-- highlight: { area: { fill: "none" } }, -->

            {#snippet tooltip()}
                <Chart.Tooltip />
            {/snippet}
        </BarChart>
    </Chart.Container>
</div>