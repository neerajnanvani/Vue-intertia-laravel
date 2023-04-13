
<template>
    <div class="min-h-full flex flex-col justify-center py-12 sm:px-6 lg:px-8">
        <div class="sm:mx-auto sm:w-full sm:max-w-md">
            <Link href="/">
                <img class="mx-auto h-12 w-auto" src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
                alt="Workflow" />
            </Link>
            <h2 class="mt-6 text-center text-3xl font-extrabold text-gray-900">
                Register a new account
            </h2>
           
        </div>

        <div class="mt-8 sm:mx-auto sm:w-full sm:max-w-md">
            <div class="bg-white py-8 px-4 shadow sm:rounded-lg sm:px-10">
                <form class="space-y-6" @submit.prevent="form.post('/register')">
                    <div>
                        <label for="name" class="block text-sm font-medium text-gray-700">
                            Name
                        </label>
                        <div class="mt-1">
                            <input v-model="form.name" id="name" name="name" type="text" autocomplete="name" 
                                class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" />
                        </div>
                        <div v-if="form.errors.name">{{ form.errors.name }}</div>
                    </div>
                    <div>
                        <label for="email" class="block text-sm font-medium text-gray-700">
                            Email address
                        </label>
                        <div class="mt-1">
                            <input v-model="form.email" id="email" name="email" type="email" autocomplete="email" 
                                class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" />
                        </div>
                        <div v-if="form.errors.email">{{ form.errors.email }}</div>
                    </div>
                    <div>
                        <label for="password" class="block text-sm font-medium text-gray-700">
                            Password
                        </label>
                        <div class="mt-1">
                            <input v-model="form.password" id="password" name="password" type="password" 
                                class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" />
                        </div>
                        <div v-if="form.errors.password">{{ form.errors.password }}</div>
                    </div>

                    <div>
                        <label for="password_confirmation" class="block text-sm font-medium text-gray-700">
                            Confirm Password
                        </label>
                        <div class="mt-1">
                            <input v-model="form.password_confirmation" id="password_confirmation" name="password_confirmation" type="password"
                                class="appearance-none block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" />
                        </div>
                        <div v-if="form.errors.password_confirmation">{{ form.errors.password_confirmation }}</div>
                    </div>

                    <div class="flex items-end justify-between">

                        <div class="text-sm">
                            <Link href="/login" class="font-medium text-indigo-600 hover:text-indigo-500">
                                Already Registered, Login?
                            </Link>
                        </div>
                    </div>

                    <div>
                        <button type="submit"
                            class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                           Register
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>
<script setup>

import { useForm, Link } from '@inertiajs/vue3'

const form = useForm({
    name: null,
    email: null,
  password: null,
  password_confirmation: null,
})

</script>