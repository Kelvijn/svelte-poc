<script>
    import { fade } from 'svelte/transition';
    import SolutionsFlyout from "./SolutionsFlyoutLarge.svelte";
    import MoreFlyout from "./MoreFlyout.svelte";
    import SolutionsFlyoutSmall from "./SolutionsFlyoutSmall.svelte";
    export let visibleSollutions = false;
    export let visibleMore = false;

    function handleVisibleClickSolutions() {
        visibleSollutions = !visibleSollutions
    }
    function handleVisibleClickMore() {
        visibleMore = !visibleMore
    }
</script>
<!-- This example requires Tailwind CSS v2.0+ -->
<div class="relative bg-white">
    <div class="flex justify-between items-center px-4 py-6 sm:px-6 md:justify-start md:space-x-10">
        <div>
            <a href="#" class="flex">
                <span class="sr-only">Workflow</span>
                <img class="h-8 w-auto sm:h-10" src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg" alt="">
            </a>
        </div>
        <div class="-mr-2 -my-2 md:hidden">
            <button on:click={handleVisibleClickSolutions} type="button" class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500" aria-expanded="false">
                <span class="sr-only">Open menu</span>
                <!-- Heroicon name: outline/menu -->
                <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
            </button>
        </div>
        <div class="hidden md:flex-1 md:flex md:items-center md:justify-between">
            <nav class="flex space-x-10">
                <div class="relative">
                    <!-- Item active: "text-gray-900", Item inactive: "text-gray-500" -->
                    <button type="button" class="text-gray-500 group bg-white rounded-md inline-flex items-center text-base font-medium hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500" aria-expanded="false"
                            on:click={handleVisibleClickSolutions}
                    >
                        <span>Solutions</span>
                        <!--
                          Heroicon name: solid/chevron-down

                          Item active: "text-gray-600", Item inactive: "text-gray-400"
                        -->
                        <svg class="text-gray-400 ml-2 h-5 w-5 group-hover:text-gray-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                            <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                        </svg>
                    </button>

                    {#if visibleSollutions}
                        <SolutionsFlyout/>
                    {/if}
                </div>
                <a href="#" class="text-base font-medium text-gray-500 hover:text-gray-900">
                    Pricing
                </a>
                <a href="#" class="text-base font-medium text-gray-500 hover:text-gray-900">
                    Docs
                </a>

                <div class="relative">
                    <!-- Item active: "text-gray-900", Item inactive: "text-gray-500" -->
                    <button on:click={handleVisibleClickMore} type="button" class="text-gray-500 group bg-white rounded-md inline-flex items-center text-base font-medium hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500" aria-expanded="false">
                        <span>More</span>
                        <!--
                          Heroicon name: solid/chevron-down

                          Item active: "text-gray-600", Item inactive: "text-gray-400"
                        -->
                        <svg class="text-gray-400 ml-2 h-5 w-5 group-hover:text-gray-500" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                            <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                        </svg>
                    </button>


                    {#if visibleMore}
                        <MoreFlyout/>
                        {/if}
                </div>
            </nav>
            <div class="flex items-center md:ml-12">
                <a href="#" class="text-base font-medium text-gray-500 hover:text-gray-900">
                    Sign in
                </a>
                <a href="#" class="ml-8 inline-flex items-center justify-center px-4 py-2 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-indigo-600 hover:bg-indigo-700">
                    Sign up
                </a>
            </div>
        </div>
    </div>

    <!--
      Mobile menu, show/hide based on mobile menu state.

      Entering: "duration-200 ease-out"
        From: "opacity-0 scale-95"
        To: "opacity-100 scale-100"
      Leaving: "duration-100 ease-in"
        From: "opacity-100 scale-100"
        To: "opacity-0 scale-95"
    -->

    <div class="absolute top-0 inset-x-0 p-2 transition transform origin-top-right md:hidden">
        <div class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 bg-white divide-y-2 divide-gray-50">
            <div class="pt-5 pb-6 px-5">
                <div class="flex items-center justify-between">
                    <div>
                        <img class="h-8 w-auto" src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg" alt="Workflow">
                    </div>
                    {#if visibleSollutions}
                    <div on:click={handleVisibleClickSolutions} class="-mr-2">
                        <button type="button" class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
                            <span class="sr-only">Close menu</span>
                            <!-- Heroicon name: outline/x -->
                            <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                            </svg>
                        </button>
                    </div>
                    {:else}
                        <div on:click={handleVisibleClickSolutions} class="-mr-2">
                            <button type="button" class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
                                <span class="sr-only">Open menu</span>
                                <!-- Heroicon name: outline/x -->
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                                </svg>
                            </button>
                        </div>
                    {/if}
                </div>
                {#if visibleSollutions}
                    <SolutionsFlyoutSmall/>
                {/if}
            </div>
            <div class="py-6 px-5">
                <div class="grid grid-cols-2 gap-4">
                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Pricing
                    </a>

                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Docs
                    </a>

                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Enterprise
                    </a>

                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Help Center
                    </a>

                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Guides
                    </a>

                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Events
                    </a>

                    <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Security
                    </a>
                </div>
                <div class="mt-6">
                    <a href="#" class="w-full flex items-center justify-center px-4 py-2 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-indigo-600 hover:bg-indigo-700">
                        Sign up
                    </a>
                    <p class="mt-6 text-center text-base font-medium text-gray-500">
                        Existing customer?
                        <a href="#" class="text-indigo-600 hover:text-indigo-500">
                            Sign in
                        </a>
                    </p>
                </div>
            </div>
        </div>
    </div>
</div>
