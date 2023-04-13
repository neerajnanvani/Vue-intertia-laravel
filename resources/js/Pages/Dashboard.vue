    <!-- This example requires Tailwind CSS v2.0+ -->
<template>
    <div class="bg-white">
        <Link href="/">
        <img class="mx-auto h-12 w-auto" src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
            alt="Workflow" />
        </Link>

        <div class="max-w-7xl mx-auto text-center py-12 px-4 sm:px-6 lg:py-16 lg:px-8">
            <h2 v-if="user" class="text-3xl font-extrabold tracking-tight text-gray-900 sm:text-4xl">
                <span class="block">Welcome </span>
                <span class="block">{{ user.name }}</span>
            </h2>
            <div class="mt-8 flex justify-center">
                <div class="inline-flex rounded-md shadow">
                    <Link v-if="user.email_verified_at === null"  href="/email/verification-notification" method="post" as="button" type="button"
                        class="inline-flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700">
                    Verify
                    </Link>
                    <Link v-else  href="/profile" 
                        class="inline-flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700">
                    Go to Profile
                    </Link>
                </div>
                <div class="ml-3 inline-flex">
                    <Link href="/logout" method="post" as="button" type="button"
                        class="inline-flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-indigo-700 bg-indigo-100 hover:bg-indigo-200">
                    Log out
                    </Link>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup>
import { usePage, Link } from '@inertiajs/vue3';
import { computed } from "vue"

const user = computed(() => usePage().props.auth.user)


</script>