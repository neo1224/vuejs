<script setup lang="ts">
import AppLayout from '@/layouts/AppLayout.vue';
import { dashboard } from '@/routes';
import { User, type BreadcrumbItem } from '@/types';
import { Head } from '@inertiajs/vue3';
import PlaceholderPattern from '../components/PlaceholderPattern.vue';

const breadcrumbs: BreadcrumbItem[] = [
    {
        title: 'Dashboard',
        href: dashboard().url,
    },
];

const user:  User = 
    {
        id: 1,
        name: 'Test Person',      
        email: 'random@email.com',
        created_at: '2024-01-15',
        updated_at: '2024-01-15',
        email_verified_at: '2024-01-15',
    };
</script>

<template>
    <Head title="Dashboard" />

    <AppLayout :breadcrumbs="breadcrumbs">
        <div
            class="flex h-full flex-1 flex-col gap-4 overflow-x-auto rounded-xl p-4"
        >
            <div class="mb-4 text-2xl font-semibold">User list</div>
    <table class="min-w-full divide-y divide-gray-200 border border-gray-300 rounded-md">
      <thead class="bg-gray-100">
        <tr>
          <th class="px-4 py-2 text-left text-sm font-semibold text-gray-700">ID</th>
          <th class="px-4 py-2 text-left text-sm font-semibold text-gray-700">Name</th>
          <th class="px-4 py-2 text-left text-sm font-semibold text-gray-700">Email</th>
          <th class="px-4 py-2 text-left text-sm font-semibold text-gray-700">Date Joined</th>
        </tr>
      </thead>
      <tbody class="bg-white divide-y divide-gray-200">
        <tr>
          <td class="px-4 py-2 text-sm text-gray-800">{{ user.id }}</td>
          <td class="px-4 py-2 text-sm text-gray-800">{{ user.name }}</td>
          <td class="px-4 py-2 text-sm text-gray-800">{{ user.email }}</td>
          <td class="px-4 py-2 text-sm text-gray-800">{{ user.created_at }}</td>
        </tr>
      </tbody>
    </table>
    
            <div class="grid auto-rows-min gap-4 md:grid-cols-3">
                <div
                    class="relative aspect-video overflow-hidden rounded-xl border border-sidebar-border/70 dark:border-sidebar-border"
                >
                    <PlaceholderPattern />
                </div>
                <div
                    class="relative aspect-video overflow-hidden rounded-xl border border-sidebar-border/70 dark:border-sidebar-border"
                >
                    <PlaceholderPattern />
                </div>
                <div
                    class="relative aspect-video overflow-hidden rounded-xl border border-sidebar-border/70 dark:border-sidebar-border"
                >
                    <PlaceholderPattern />
                </div>
            </div>
            <div
                class="relative min-h-[100vh] flex-1 rounded-xl border border-sidebar-border/70 md:min-h-min dark:border-sidebar-border"
            >
                <PlaceholderPattern />
            </div>
        </div>
    </AppLayout>
</template>
