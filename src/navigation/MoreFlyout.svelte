<script>
    import { fade } from 'svelte/transition';
</script>


<!--
                      'More' flyout menu, show/hide based on flyout menu state.

                      Entering: "transition ease-out duration-200"
                        From: "opacity-0 translate-y-1"
                        To: "opacity-100 translate-y-0"
                      Leaving: "transition ease-in duration-150"
                        From: "opacity-100 translate-y-0"
                        To: "opacity-0 translate-y-1"
                    -->

<div transition:fade class="absolute z-10 left-1/2 transform -translate-x-1/2 mt-3 px-2 w-screen max-w-xs sm:px-0"
>
    <div class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 overflow-hidden">
        <div class="relative grid gap-6 bg-white px-5 py-6 sm:gap-8 sm:p-8">
            <a href="#" class="-m-3 p-3 block rounded-md hover:bg-gray-50">
                <p class="text-base font-medium text-gray-900">
                    Help Center
                </p>
                <p class="mt-1 text-sm text-gray-500">
                    Get all of your questions answered in our forums or contact support.
                </p>
            </a>

            <a href="#" class="-m-3 p-3 block rounded-md hover:bg-gray-50">
                <p class="text-base font-medium text-gray-900">
                    Guides
                </p>
                <p class="mt-1 text-sm text-gray-500">
                    Learn how to maximize our platform to get the most out of it.
                </p>
            </a>

            <a href="#" class="-m-3 p-3 block rounded-md hover:bg-gray-50">
                <p class="text-base font-medium text-gray-900">
                    Events
                </p>
                <p class="mt-1 text-sm text-gray-500">
                    See what meet-ups and other events we might be planning near you.
                </p>
            </a>

            <a href="#" class="-m-3 p-3 block rounded-md hover:bg-gray-50">
                <p class="text-base font-medium text-gray-900">
                    Security
                </p>
                <p class="mt-1 text-sm text-gray-500">
                    Understand how we take your privacy seriously.
                </p>
            </a>
        </div>
    </div>
</div>