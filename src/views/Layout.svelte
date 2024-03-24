<script>
    import Page2 from "./Page2.svelte";
    import Router from "svelte-spa-router";
    import Page from "./Page.svelte";
    import SidebarNav from "../components/SidebarNav.svelte";


    const prefix = '/'
    const routes = {
        '/': Page,
        '/page2': Page2,
    }

    const sidebarNavItems = [
        {
            title: "Page1",
            href: "/",
        }, {
            title: "Page2",
            href: "/page2",
        }
    ]

</script>
<div class=" space-y-6 p-4 pb-16 md:block">
    <div class="flex flex-row items-start gap-6">
        <aside>
            <SidebarNav items={sidebarNavItems}/>
        </aside>
        <div class="flex-1 ">
            <Router {routes}/>
        </div>
    </div>
</div>
