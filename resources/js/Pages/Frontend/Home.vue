<template>
    
    <Frontend>
        <Head title="Home" />
        This is From <b>{{title}}</b> Page
        
    </Frontend>
</template>

<script setup>
    import Frontend from '@/Layouts/FrontendLayout.vue';
    import { Head} from '@inertiajs/vue3';

    defineProps({
        title: String
    });
</script>

<style lang="scss" scoped>

</style>