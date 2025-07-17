<template>
    <Head title="Products" />
    <Frontend>
        <div class="container mx-auto px-4 mt-4">
            <div v-if="$page.props.flash.message" class="alert bg-green-200 mt-4 mx-auto px-4 py-2 rounded mb-3">
                {{ $page.props.flash.message }}
            </div>
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
                    <tr v-for="(item, index) in products"
                        :key="index"
                    >
                        <td class="border-b px-4 py-2">{{ item.id }}</td>
                        <td class="border-b px-4 py-2">{{ item.name }}</td>
                        <td class="border-b px-4 py-2">${{ item.price }}</td>
                        <td class="border-b px-4 py-2">
                            <Link :href="route('products.show', item.id)" class="whitespace-nowrap text-white rounded inline-block px-2 py-1 bg-blue-500 hover:bg-gray-700">Show</Link>
                            <Link :href="route('products.edit', item.id)" class="ml-2 whitespace-nowrap text-white rounded inline-block px-2 py-1 bg-green-500 hover:bg-green-600">Edit</Link>
                            <Link :href="route('products.destroy', item.id)" class="ml-2 whitespace-nowrap text-white rounded inline-block px-2 py-1 bg-red-500 hover:bg-red-600">Delete</Link>
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

defineProps({
    products: Array,
})
</script>