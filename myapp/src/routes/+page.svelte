<script>
    // import components
    import StepComponent from '../components/StepComponent.svelte';
    import StepTracker from '../components/StepTracker.svelte';

    import "../app.css";

    export const steps = [
        {
            stepNumber: 1,
            stepTitle: 'Your info'
        },
        {
            stepNumber: 2,
            stepTitle: 'Select plan'
        },
        {
            stepNumber: 3,
            stepTitle: 'Add-ons'
        },
        {
            stepNumber: 4,
            stepTitle: 'Summary'
        }
    ]

    const stepIncrement = () => {
        if (stepIndex < 3) {
            stepIndex = stepIndex + 1;
        }
    }

    const stepDecrement = () => {
        if (stepIndex > 0) {
            stepIndex = stepIndex - 1;
        }
    }

    let stepIndex = 0
</script>

<!-- start of wrapper div -->
<main class="max-w-screen-lg mx-auto">
    <section class="grid grid-cols-3 rounded-2xl bg-white">
        <StepTracker 
            {steps} 
            stepNumber={stepIndex + 1}
        />
        <StepComponent
            stepNumber={stepIndex + 1}
            stepIncrement={() => stepIncrement()}
            stepDecrement={() => stepDecrement()}
        />
    </section>
</main>
<!-- end of wrapper div -->