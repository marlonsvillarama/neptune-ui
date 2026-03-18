<script>
    import * as DropdownMenu from '@/components/ui/dropdown-menu/index';
    import Button from '../ui/button/button.svelte';
    import {
        Building2,
        ChartNoAxesCombined,
        Menu
    } from '@lucide/svelte';
</script>

<header class="bg-deep-neptune py-3">
    <div class="container text-background flex items-center justify-between">
        <div class="flex items-center gap-8">
            <DropdownMenu.Root>
                <DropdownMenu.Trigger>
                    <Button class="bg-deep-neptune hover:bg-horizon-blue cursor-pointer">
                        <Menu />
                    </Button>
                </DropdownMenu.Trigger>
            </DropdownMenu.Root>

            <div class="header-title flex items-center gap-3">
                <ChartNoAxesCombined size={32} class="bg-muted-foreground rounded-sm p-1.5" />
                <div class="grid gap-0">
                    <span class="title text-lg">
                        360<sup>o</sup> Assessment Dashboard
                    </span>
                    <span class="sub-title text-xs text-frost-white/80">
                        Real-time performance monitoring
                    </span>
                </div>
            </div>
        </div>

        <Button class="bg-ocean-core hover:bg-horizon-blue text-white flex gap-2 items-center">
            <Building2 size={20} />
            <span class="font-light text-xs tracking-[0.25px]">Neptune Dynamics</span>
        </Button>
    </div>
</header>

<style>
</style>