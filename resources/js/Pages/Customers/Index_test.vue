<script setup>
import FlashMessage from '@/Components/FlashMessage.vue';
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import Pagination from '@/Components/Pagination.vue';
import { Head, Link } from '@inertiajs/inertia-vue3';

defineProps({
    customers: Object
})

</script>

<template>
    <ul v-for="customer in customers.data" :key="customer.id">
        <li>{{ customer.id }}</li>
        <li>{{ customer.name }}</li>
    </ul>
    <Pagination class="mt-6" :links="customers.links"></Pagination>
</template>
