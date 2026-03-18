<script>
    import {
        CircleDollarSign,
        TrendingUp
    } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
    import Badge from '@/components/ui/badge/badge.svelte';
</script>

<Card.Root class="">
    <Card.Content class="grid gap-6 pb-1">
        <div class="flex items-center justify-between">
            <div class="flex items-center gap-2">
                <CircleDollarSign size={24} class="text-muted-foreground" />
                <h2 class="text-xs text-muted-foreground uppercase">Money Spent</h2>
            </div>
            <!-- <Badge variant="outline">
                <TrendingUp /> +25%
            </Badge> -->
        </div>
        <div class="items-center flex flex-col gap-4 pb-2">
            <h1 class="text-5xl font-bold text-primary/80">60,000</h1>
            <Badge variant="outline">
                <TrendingUp /> +25% from last quarter
            </Badge>
            <!-- <span class="uppercase">From last quarter</span> -->
        </div>
    </Card.Content>
</Card.Root>
