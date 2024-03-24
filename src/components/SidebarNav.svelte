<script>
    import {location} from 'svelte-spa-router'
    import { createCollapsible, melt } from '@melt-ui/svelte';
    import Button from './Button.svelte';

    const {
        elements: { root, content, trigger },
        states: { open }
    } = createCollapsible()
    export let items = [];
    //
    $: activeUrl = window.location.pathname;


</script>

<!-- Using Svelte Scoped Styles -->
<div class="root" use:melt={$root}>
    <!-- Using an external component -->
    <Button on:click={() => console.log('clicked')} {...$trigger} action={trigger}>
        {$open ? 'Close' : 'Open'}
    </Button>
    <!-- Using an utility class library, such as Tailwind -->
    <div class="rounded-md p-4 text-orange-500 shadow-sm" use:melt={$content}>
        Obi-Wan says: Hello there!
    </div>
</div>


<style>
    .root {
        display: flex;
        flex-direction: column;
    }
</style>
