<template>
    <nav class="bg-gray-200">
        <div class="container mx-auto flex items-center justify-between px-4 py-3">
            <div class="text-lg font-semibold">
                Logo
            </div>
            <div>
                <ul class="flex gap-x-4">
                    <li>
                        <Link class="px-2 py-1 text-gray-800 hover:text-blue-600" :href="route('home')">Home</Link>
                    </li>
                    <li>
                        <Link class="px-2 py-1 text-gray-800 hover:text-blue-600" :href="route('about')">About</Link>
                    </li>
                    <li>
                        <Link class="px-2 py-1 text-gray-800 hover:text-blue-600" :href="route('contact')">Contact</Link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script setup>
    import { Link } from '@inertiajs/vue3';
</script>