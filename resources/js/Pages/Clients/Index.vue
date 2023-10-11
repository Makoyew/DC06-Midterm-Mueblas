<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { defineProps } from 'vue';


const { clients } = defineProps(['clients']);
</script>

<template>
    <Head title="Clients" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">Clients</h2>
        </template>

        <div>
    <table class="min-w-full divide-y divide-gray-200">
      <thead>
        <tr>
          <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50">ID</th>
          <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50">Last Name</th>
          <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50">First Name</th>
          <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50">Address</th>
          <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50">Phone</th>
          <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50">Credit Limit</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="client in clients" :key="client.id">
          <td class="px-6 py-4 whitespace-no-wrap">{{ client.id }}</td>
          <td class="px-6 py-4 whitespace-no-wrap">{{ client.last_name }}</td>
          <td class="px-6 py-4 whitespace-no-wrap">{{ client.first_name }}</td>
          <td class="px-6 py-4 whitespace-no-wrap">{{ client.address }}</td>
          <td class="px-6 py-4 whitespace-no-wrap">{{ client.phone }}</td>
          <td class="px-6 py-4 whitespace-no-wrap">{{ client.credit_limit }}</td>
        </tr>
      </tbody>
    </table>
  </div>
    </AuthenticatedLayout>
</template>
