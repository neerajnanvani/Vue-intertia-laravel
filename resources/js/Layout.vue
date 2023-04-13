<script setup>
import { Link } from '@inertiajs/vue3'
</script>

<template>
  <main>
    <header>
      <Link href="/">Home</Link>
      <Link href="/login">About</Link>
      <Link href="/register">Contact</Link>
    </header>
    <article>
      <slot />
    </article>
  </main>
</template>