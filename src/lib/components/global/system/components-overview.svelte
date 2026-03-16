<script>
    import { CircleQuestionMark } from '@lucide/svelte';
    import * as Card from '@/components/ui/card/index';
    import Button from '@/components/ui/button/button.svelte';
    import Separator from '@/components/ui/separator/separator.svelte';
    import ComponentsItem from './components-item.svelte';
</script>

<Card.Root>
    <Card.Content>
        <div class="flex items-center gap-3">
            <span class="text-lg font-semibold">System Components</span>
            <Button variant="ghost" size="icon" class="p-0 rounded-[50%]">
                <CircleQuestionMark class="text-muted-foreground cursor-pointer" />
            </Button>
        </div>

        <div class="grid gap-3 my-3">
            <!-- Table Header -->
            <div class="grid-header grid grid-cols-[2fr_5fr_2fr] gap-12">
                <span class="text-md font-semibold">Area</span>
                <span class="text-md font-semibold">Optimization Status</span>
                <span class="text-md font-semibold text-center">Impact</span>
            </div>
            
            <Separator />

            <ComponentsItem title="Record Operations"
                attention={['1']}
                progress={60}
                status='critical'
                impact='high'
            />

            <Separator />

            <ComponentsItem title="Security"
                progress={100}
            />

            <Separator />

            <ComponentsItem title="Integrations"
                progress={100}
            />

            <Separator />

            <ComponentsItem title="Backend Scripts"
                attention={['1']}
                progress={72}
                status='review'
                impact='medium'
            />
        </div>

    </Card.Content>
</Card.Root>
