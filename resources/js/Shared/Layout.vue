<template>

    <Head>
        <title>My App</title>
    </Head>
    <section class="p-6 bg-indigo-900 text-white">
    <header class="flex justify-between">
        <div class="flex items-center">
            <Link href="/" class="font-bold text-lg">
                My App
            </Link>

            <p class="text-sm ml-4">
                Welcome Back, {{ username }}!
            </p>
        </div>
        <Nav />
    </header>
    </section>

    <section class="p-6">
        <div class="max-w-3xl mx-auto">
            <slot/>
        </div>
    </section>
</template>

<script>
import Nav from "./Nav"
import { Head } from "@inertiajs/inertia-vue3"

export default {
    components: {
        Nav,
        Head
    },
    computed: {
        username() {
            return this.$page.props.auth.user.username;
        }
    }
}
</script>
