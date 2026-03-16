<script>
    import {
        Clock,
        TrendingUp
    } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
    import Badge from '@/components/ui/badge/badge.svelte';
</script>

<Card.Root>
    <Card.Content class="grid gap-6 pb-1">
        <div class="flex items-center justify-between">
            <div class="flex items-center gap-2">
                <Clock size={24} class="text-muted-foreground" />
                <h2 class="text-sm text-muted-foreground uppercase">Time Saved</h2>
            </div>
            <Badge variant="outline">
                60/100
            </Badge>
        </div>
        <div class="items-center flex flex-col gap-4 pb-2">
            <h1 class="text-5xl font-bold">300 hrs</h1>
            <Badge variant="outline">
                12.5 days recovered
            </Badge>
        </div>
    </Card.Content>
</Card.Root>
