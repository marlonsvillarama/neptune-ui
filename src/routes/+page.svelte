<script>
    import ComponentsOverview from "@/components/global/system/components-overview.svelte";
    import KpiSet from "@/components/global/kpi/kpi-set.svelte";
    import PageTitle from "@/components/global/page-title.svelte";
    import RecordsOverview from "@/components/global/optimization/records-overview.svelte";
    import StartOptimization from "@/components/global/optimization/start-optimization.svelte";
</script>

<div class="grid gap-6 pb-8">
    <PageTitle />
    <KpiSet />
    <ComponentsOverview />
    <RecordsOverview />
    <StartOptimization />
</div>
