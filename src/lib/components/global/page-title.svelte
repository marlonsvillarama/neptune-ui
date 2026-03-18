<script>
    import {
        ArrowDownToLine,
        CalendarFold
    } from "@lucide/svelte";
    import * as Popover from "@/components/ui/popover/index";
    import Button from "@/components/ui/button/button.svelte";
    import Calendar from "@/components/ui/calendar/calendar.svelte";
    import { buttonVariants } from "@/components/ui/button/button.svelte";
    import { CalendarDate } from "@internationalized/date";

    let {
        value = new Date()
    } = $props();

    let rangeValues = $derived.by(() => {
        let dt = new Date(value.getFullYear(), value.getMonth(), value.getDate());
        dt.setDate(-7);
        return [ value, dt ];
    });
    let placeholder = $derived(rangeValues[0]);
</script>

<div class="flex items-center justify-between">
    <div class="grid gap-1">
        <h1 class="text-2xl tracking-wide">System Optimization Report</h1>

        <div class="flex items-center gap-4">
            <!-- <div class="flex items-center gap-2 text-muted-foreground"> -->
                <!-- <CalendarFold size={16} /> -->
                <span class="text-muted-foreground">Oct 11, 2025 - Nov 12, 2025</span>
            <!-- </div> -->
            <Popover.Root class="inline">
                <Popover.Trigger class={buttonVariants({ variant: "outline", size:"xs" })}>
                    <div class="flex items-center gap-1 text-muted-foreground">
                        <CalendarFold size={16} />
                        <span class="text-xs">Change</span>
                    </div>
                </Popover.Trigger>
                <Popover.Content>
                    <Calendar type="multiple"
                        bind:value
                        bind:placeholder
                        numberOfMonths={2}
                    />
                </Popover.Content>
            </Popover.Root>
        </div>
    </div>

    <!-- <Button variant="outline" class="bg-ocean-core hover:bg-horizon-blue hover:shadow-sm"> -->
    <Button variant="outline">
        <ArrowDownToLine size={16} />
        <span class="text-xs">Download as PDF</span>
    </Button>
</div>
