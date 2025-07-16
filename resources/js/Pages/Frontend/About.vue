<template>
    
    <Frontend>
        <Head title="About" />
        
        This is From <b>{{title}}</b> Page
    </Frontend>
</template>

<script setup>
    import { Head} from '@inertiajs/vue3';
    import Frontend from '@/Layouts/FrontendLayout.vue';
    defineProps({
        title: String
    });
</script>

<style lang="scss" scoped>

</style>