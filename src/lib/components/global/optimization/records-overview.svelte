<script>
    import RecordsCurrent from './records-current.svelte';
    import RecordsNeptune from './records-neptune.svelte';
    import RecordsAdditional from './records-additional.svelte';
    import { CircleQuestionMark } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
    import Button from '@/components/ui/button/button.svelte';

</script>

<Card.Root>
    <Card.Content class="grid gap-12">
        <section class="grid gap-5">
            <div class="header grid">
                <div class="flex items-center gap-3">
                    <span class="text-lg font-semibold">Records Operations Optimization</span>
                    <Button variant="ghost" size="icon" class="p-0 rounded-[50%]">
                        <CircleQuestionMark class="text-muted-foreground cursor-pointer" />
                    </Button>
                </div>
                <span class="text-muted-foreground">We've analyzed the slowest record in your account. Here is how optimization can help.</span>
            </div>

            <!-- <div class="grid grid-cols-[repeat(2,1fr)] gap-8"> -->
                <!-- <RecordsCurrent /> -->
                <!-- <RecordsNeptune /> -->
            <!-- </div> -->
        </section>

        <RecordsAdditional />
    </Card.Content>
</Card.Root>
