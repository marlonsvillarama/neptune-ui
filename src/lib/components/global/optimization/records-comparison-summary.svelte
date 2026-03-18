<script>
    import {
        CircleDollarSign,
        Clock
    } from "@lucide/svelte";
    import Badge from "@/components/ui/badge/badge.svelte";
    import Separator from "@/components/ui/separator/separator.svelte";
</script>

<!-- <div class="flex flex-col border-2 border-t-6 border-green rounded-sm pt-3 px-4 pb-5"> -->
<div class="flex flex-col gap-12 border rounded-sm pt-3 px-4 pb-5">
    <!-- <div class="flex items-center justify-between"> -->
        <!-- <div class="flex items-center gap-2"> -->
            <!-- <FileText size={24} class="text-muted-foreground" /> -->
        <!-- </div> -->
        <!-- <Badge variant="default text-xs">
            <span class="uppercase">{badge}</span>
        </Badge> -->
    <!-- </div> -->
    <div class="flex flex-col gap-2">
        <span class="text-md">Affected Areas</span>
        <div class="flex gap-4">
            <Badge variant="red">Integrations</Badge>
            <Badge variant="red">CSV Imports</Badge>
            <Badge variant="red">Backend</Badge>
            <Badge variant="red">Batch Processes</Badge>
        </div>
    </div>
    <!-- <Separator class="my-6" /> -->
    <div class="grid gap-6">
        <span class="text-md">Estimated Monthly Savings</span>
        <div class="grid grid-cols-[repeat(2,1fr)] gap-6 items-center">
            <div class="border">

            </div>
            <div class="border">2</div>
        </div>
    </div>
</div>

{#snippet savings (icon, title, text)}
<div>
    <div class="grid grid-cols-[1fr,8fr] gap-3 items-center">
        <CircleDollarSign size={20} />
        <span class="text-muted-foreground">{title}</span>
    </div>
    <div class="grid grid-cols-[1fr,8fr] gap-3 items-center">
        <span>&nbsp;</span>
        <span class="text-lg font-semibold">{text}</span>
    </div>
</div>
{/snippet}