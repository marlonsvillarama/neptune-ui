<script>
    import { CircleQuestionMark } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
</script>

<Card.Root>
    <Card.Content>
        <div class="flex items-center gap-3">
            <span class="text-lg font-semibold">Records Operations Optimization</span>
            <CircleQuestionMark class="text-muted-foreground cursor-pointer" />
        </div>
    </Card.Content>
</Card.Root>