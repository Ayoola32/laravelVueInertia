<template>
    <Head title="Products" />
    <Frontend>
        <div class="container mx-auto px-4 mt-4">
            <div class="flex items-center justify-between">
                <h5 class="text-lg font-semibold">Product Lists</h5>
                <Link :href="route('products.create')" class="rounded bg-gray-500 px-4 py-2 text-white hover:bg-gray-600">
                    Add New Product
                </Link>
            </div>
            <table class="mt-4 table-auto border border-gray-200 bg-white shadow w-full">
                <thead>
                    <tr>
                        <th class="border-b px-4 py-2 text-left">#</th>
                        <th class="border-b px-4 py-2 text-left">Name</th>
                        <th class="border-b px-4 py-2 text-left">Price</th>
                        <th class="border-b px-4 py-2 text-left">Action</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="border-b px-4 py-2">1</td>
                        <td class="border-b px-4 py-2">Apple</td>
                        <td class="border-b px-4 py-2">$1.99</td>
                        <td class="border-b px-4 py-2">
                            <Link :href="route('products.show', 1)" class="whitespace-nowrap text-white rounded inline-block px-2 py-1 bg-gray-500 hover:bg-gray-700">Show</Link>
                            <Link :href="route('products.edit', 1)" class="ml-2 whitespace-nowrap text-white rounded inline-block px-2 py-1 bg-green-500 hover:bg-green-600">Edit</Link>
                            <Link :href="route('products.destroy', 1)" class="ml-2 whitespace-nowrap text-white rounded inline-block px-2 py-1 bg-red-500 hover:bg-red-600">Delete</Link>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </Frontend>
</template>


<script setup>
import { Head, Link } from '@inertiajs/vue3';
import Frontend from '@/Layouts/FrontendLayout.vue';
</script>