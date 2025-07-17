<script setup>
    import { Head, Link, useForm } from "@inertiajs/vue3";
    import Frontend from "@/Layouts/FrontendLayout.vue";

    const  props = defineProps({ 
        errors: Object, 
        product: Object,
    });

    const form = useForm({
        name: props.product.name,
        price: props.product.price,
    });

    const updateProduct = () => {
        form.put(route('products.update', props.product.id), {
            onSuccess: () => form.reset(),
        });
    }

</script>



<template>
    <Head title="Edit Product" />
    <Frontend>
        <div v-if="$page.props.flash.message" class="alert">
            {{ $page.props.flash.message }}
        </div>

        <div class="container mx-auto px-4 mt-4">
            <div class="flex items-center justify-between">
                <h5 class="text-lg font-semibold">Update Product</h5>
                <Link
                    :href="route('products.index')"
                    class="rounded bg-gray-500 px-4 py-2 text-white hover:bg-gray-600"
                >
                    Back
                </Link>
            </div>

            <form @submit.prevent="updateProduct()">
                <div class="grid grid-cols-12 gap-4">
                    <div class="col-span-6">
                        <div class="sm:col-span-3 mb-5">
                            <label
                                for="product-name"
                                class="block text-sm/6 font-medium text-gray-900"
                                >Product Name</label
                            >
                            <div class="mt-2">
                                <input
                                    id="product-name"
                                    v-model="form.name"
                                    type="text"
                                    name="name"
                                    autocomplete="family-name"
                                    class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6"
                                />
                            </div>
                            <div v-if="errors.name" class="text-red-500">{{ errors.name }}</div>
                        </div>
                        <div class="sm:col-span-3">
                            <label
                                for="product-price"
                                class="block text-sm/6 font-medium text-gray-900"
                                >Product Price</label
                            >
                            <div class="mt-2">
                                <input
                                    id="product-price"
                                    v-model="form.price"
                                    type="number"
                                    name="price"
                                    autocomplete="family-name"
                                    class="block w-full rounded-md bg-white px-3 py-1.5 text-base text-gray-900 outline-1 -outline-offset-1 outline-gray-300 placeholder:text-gray-400 focus:outline-2 focus:-outline-offset-2 focus:outline-indigo-600 sm:text-sm/6"
                                />
                            </div>
                            <div v-if="errors.price" class="text-red-500">{{ errors.price }}</div>
                        </div>
                        <div class="sm:col-span-3">
                            <div class="mt-4">
                                <button type="submit" class="rounded bg-blue-500 px-4 py-2 text-white hover:bg-gray-600">
                                    Update
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </form>
        </div>
    </Frontend>
</template>


