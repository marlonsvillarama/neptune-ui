<script>
    import { cn } from "tailwind-variants";
    import { getCoreRowModel } from "@tanstack/table-core";
    import {
        createSvelteTable,
        FlexRender
    } from "@/components/ui/data-table/index";
    import * as Table from '@/components/ui/table/index';
    import { recordTypes } from "./record-types";
    // console.log('recordTypes', recordTypes);

    let {
        columns,
        data
    } = $props();

    // const table = createSvelteTable({
    //     get data() { return data },
    //     columns,
    //     getCoreRowModel: getCoreRowModel()
    // });

    const parseRowValue = (column, row) => {
        if (column.accessorKey === 'type') {
            return recordTypes[row.type].name;
        }
        if (column.accessorKey === 'eff') {
            return `${(row.eff * 100).toFixed(0)}%`;
        }
        if (column.accessorKey === 'savings') {
            return new Intl.NumberFormat('en-NZ', { style: 'currency', currency: 'NZD' }).format(row.savings);
        }
        if (column.accessorKey === 'optimized') {
            return row.optimized === true ? 'Optimized' : '';
        }
        return row[column.accessorKey];
    };
</script>

<div class="rounded-md border">
    <Table.Root>
        <Table.Header>
            <Table.Row>
                {#each columns as column}
                    <Table.Head class={[ 'type', 'status' ].indexOf(column.accessorKey) >= 0 ? '' : 'text-center'}>
                        {column.header}
                    </Table.Head>
                {/each}
            </Table.Row>
        </Table.Header>
        <Table.Body>
            {#each data as row}
                <Table.Row>
                    {#each columns as column}
                        <Table.Cell class={[ 'type', 'status' ].indexOf(column.accessorKey) >= 0 ? '' : 'text-center'}>
                            <!-- {`${column.accessorKey} = ${row[column.accessorKey]}`} -->
                            {parseRowValue(column, row)}
                        </Table.Cell>
                    {/each}
                </Table.Row>
            {:else}
                <Table.Row>
                    <Table.Cell colspan={columns.length} class="h-24 text-center">
                        No results.
                    </Table.Cell>
                </Table.Row>
            {/each}
        </Table.Body>
    </Table.Root>
</div>