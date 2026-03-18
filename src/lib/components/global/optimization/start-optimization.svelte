<script>
    import { CircleCheck } from "@lucide/svelte";
    import Button from "@/components/ui/button/button.svelte";
    import Sparkles from '@/assets/sparkles.svg';
</script>

<div class="rounded-xl border-2 border-t-6 border-blue bg-linear-to-b from-blue-light to-50% to-background px-8 py-5 flex flex-col gap-8 relative">
    <img src={Sparkles} alt="AI" class="absolute top-[1rem] right-[1rem] h-[6rem]">
    <div class="header grid gap-2">
        <span class="text-3xl font-semibold">Here's what you'll get</span>
        <span class="text-muted-foreground">Everything you need to optimize your NetSuite performance and unlock significant time and cost savings.</span>
    </div>
    
    <div class="grid gap-4">
        <div class="grid grid-cols-[1fr_1fr] gap-12">
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Full inventory and documentation of all customizations</span>
            </div>
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Rewritten customizations as event-based or scheduled processes</span>
            </div>
        </div>
        <div class="grid grid-cols-[1fr_1fr] gap-12">
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Rebuilt workflows with clear Before Submit trigger points</span>
            </div>
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Consolidated, streamlined scripts</span>
            </div>
        </div>
        <div class="grid grid-cols-[1fr_1fr] gap-12">
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Validation of native replacement options</span>
            </div>
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Upgrade to SuiteScript 2.1</span>
            </div>
        </div>
        <div class="grid grid-cols-[1fr_1fr] gap-12">
            <div class="flex items-center gap-3">
                <CircleCheck />
                <span>Context-specific deployments for forms or roles</span>
            </div>
        </div>
    </div>

    <div class="flex w-full justify-end">
        <Button class="bg-blue px-16 py-6 text-lg tracking-[0.25px] shadow-md">Start Optimization</Button>
    </div>
</div>