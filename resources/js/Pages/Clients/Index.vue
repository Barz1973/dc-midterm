<script setup>
import Layout from "@/Layouts/Layout.vue";
import Pagination from "@/Layouts/Pagination.vue";
import ClientsCard from "@/Components/ClientsCard.vue";
import { Head } from "@inertiajs/vue3";

const props = defineProps({
    clients: Object,
});
</script>

<template>
    <Head title="Clients" />
    <Layout title="Clients">
        <div class="flex justify-between bg-light-400">
            <h2 class="font-bold text-4xl text-dark ml-8 mt-4 mb-4">
                Clients List
            </h2>
        </div>
        <div class="flex justify-end">
           
        </div>

        <div class="max-w-7xl mx-auto mt-4">
            <div
                class="grid grid-cols-1 sm:grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-4"
            >
                <ClientsCard
                    v-for="client in clients.data"
                    :key="client.id"
                    :client="client"
                />
            </div>
        </div>

        <div class="flex justify-center items-center mt-4">
            <Pagination
                :links="clients.links"
                :currentPage="clients.current_page"
                :totalPages="clients.total"
                pageRange="4"
            />
        </div>
    </Layout>
</template>
