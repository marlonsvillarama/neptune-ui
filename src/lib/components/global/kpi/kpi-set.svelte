<script>
    import Separator from "@/components/ui/separator/separator.svelte";
    import KpiScore from "./kpi-score.svelte";
    import KpiMoneySaved from "./kpi-money-saved.svelte";
    import KpiTimeSaved from "./kpi-time-saved.svelte";
    import UnlockMore from "./unlock-more.svelte";
</script>

<div class="border rounded-md shadow-md grid grid-cols-[1fr_auto_1fr_auto_1fr_auto_1fr] items-center">
    <KpiScore score={80} />
    <Separator orientation="vertical"></Separator>
    <KpiMoneySaved />
    <Separator orientation="vertical"></Separator>
    <KpiTimeSaved />
    <Separator orientation="vertical"></Separator>
    <UnlockMore />
</div>
