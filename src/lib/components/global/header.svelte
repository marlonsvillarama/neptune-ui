<script>
    import * as DropdownMenu from '@/components/ui/dropdown-menu/index';
    import Button from '../ui/button/button.svelte';
    import {
        ChartNoAxesCombined,
        Menu
    } from '@lucide/svelte';
</script>

<header class="bg-[currentColor] py-3">
    <div class="container text-background flex items-center justify-between">
        <div class="flex items-center gap-6">
            <DropdownMenu.Root>
                <DropdownMenu.Trigger>
                    <Button class="bg-foreground cursor-pointer ml-[-1rem]">
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
                    <span class="sub-title text-xs text-muted-foreground">
                        Real-time performance monitoring
                    </span>
                </div>
            </div>
        </div>

        <Button variant="outline" class="bg-foreground text-white">Company X</Button>
    </div>
</header>

<style>
</style>