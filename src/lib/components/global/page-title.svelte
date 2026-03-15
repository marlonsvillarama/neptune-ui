<script>
    import {
        ArrowDownToLine,
        Calendar
    } from "@lucide/svelte";
    import Button from "../ui/button/button.svelte";
</script>

<div class="flex items-center justify-between">
    <div class="grid gap-1">
        <h1 class="text-2xl tracking-wide">System Optimization Report</h1>

        <div class="flex items-center gap-2 text-muted-foreground">
            <Calendar size={16} />
            <span>Oct 11, 2025 - Nov 12, 2025</span>
        </div>
    </div>

    <Button>
        <ArrowDownToLine size={16} />
        <span>Export</span>
    </Button>
</div>
