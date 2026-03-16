<script>
    import {
        Sparkles
    } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
    import Button from '@/components/ui/button/button.svelte';
</script>

<Card.Root>
    <Card.Content class="flex flex-col items-center gap-3 pb-1">
        <Sparkles size={32} />
        <div class="flex flex-col items-center gap-0">
            <h2 class="text-lg font-bold">Unlock more savings</h2>
            <span class="text-sm text-muted-foreground">View your opportunities</span>
        </div>
        <Button>Explore</Button>
    </Card.Content>
</Card.Root>
