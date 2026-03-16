<script>
    import Separator from "@/components/ui/separator/separator.svelte";
    import KpiScore from "./kpi-score.svelte";
    import KpiMoneySaved from "./kpi-money-saved.svelte";
    import KpiTimeSaved from "./kpi-time-saved.svelte";
    import UnlockMore from "./unlock-more.svelte";
</script>

<div class="grid grid-cols-[repeat(4,1fr)] gap-6 items-center">
    <KpiScore score={80} />
    <!-- <Separator orientation="vertical"></Separator> -->
    <KpiMoneySaved />
    <!-- <Separator orientation="vertical"></Separator> -->
    <KpiTimeSaved />
    <!-- <Separator orientation="vertical"></Separator> -->
    <UnlockMore />
</div>
