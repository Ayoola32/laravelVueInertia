<template>
    <nav class="flex items-center justify-between p-4 bg-gray-200">
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
    </nav>
</template>

<script setup>
    import { Link } from '@inertiajs/vue3';
</script>