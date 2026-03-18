<script>
    import {
        Sparkles
    } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
    import Button from '@/components/ui/button/button.svelte';
</script>

<Card.Root class="border border-2 border-t-6 border-blue bg-linear-to-b from-blue-light to-50% to-background">
    <Card.Content class="flex flex-col items-center gap-3 pb-1">
        <Sparkles size={32} />
        <div class="flex flex-col items-center gap-0">
            <h2 class="text-lg font-bold">Unlock more savings</h2>
            <span class="text-sm text-muted-foreground">View your opportunities</span>
        </div>
        <Button class="bg-ocean-core hover:bg-horizon-blue hover:shadow-sm">Explore</Button>
    </Card.Content>
</Card.Root>
