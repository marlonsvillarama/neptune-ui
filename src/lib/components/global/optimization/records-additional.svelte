<script>
    import { CircleQuestionMark } from '@lucide/svelte';
    import * as Select from '@/components/ui/select/index';
    import Button from '@/components/ui/button/button.svelte';
    import RecordsAdditionalTable from './records-additional-table.svelte';
    import { columns } from './records-additional-columns';
    
    const sortTypes = [
        { value: 'efficiency', label: 'Efficiency' },
        { value: 'savetime', label: 'Save Time' },
        { value: 'edittime', label: 'Edit Time' },
        { value: 'savings', label: 'Potential Savings' },
    ];
    let selectedSort = $state('efficiency');
    let triggerContent = $derived(
        sortTypes.find(s => s.value === selectedSort).label
    );

    const tableRows = [
        { type: 'itemfulfillment', average: 5, slowest: 7, save: 7, edit: 15, eff: 0.85, savings: 8500, optimized: true },
        { type: 'customer', average: 6, slowest: 9, save: 9, edit: 15, eff: 0.72, savings: 12000 },
        { type: 'invoice', average: 8, slowest: 12, save: 15, edit: 15, eff: 0.68, savings: 15500 },
        { type: 'salesorder', average: 15, slowest: 22, save: 15, edit: 22, eff: 0.45, savings: 28000 },
    ];
</script>

<section class="grid">
    <div class="header flex items-center justify-between">
        <div class="header grid">
            <div class="flex items-center gap-3">
                <span class="text-lg font-semibold">Additional Records</span>
                <Button variant="ghost" size="icon" class="p-0 rounded-[50%]">
                    <CircleQuestionMark class="text-muted-foreground cursor-pointer" />
                </Button>
            </div>
            <span class="text-muted-foreground">Time measurements are in seconds.</span>
        </div>

        <Select.Root type="single" bind:value={selectedSort}>
            <Select.Trigger class="w-[15rem] text-xs cursor-pointer">
                <span>Sort by <span class="font-bold">{triggerContent}</span></span>
            </Select.Trigger>
            <Select.Content>
                {#each sortTypes as st}
                    <Select.Item value={st.value} label={st.label}>{st.label}</Select.Item>
                {/each}
            </Select.Content>
        </Select.Root>
    </div>

    <RecordsAdditionalTable data={tableRows} {columns} />
</section>