<template>
    <div>
        <header>
            <h1 class="fake-logo">{{ siteName }}</h1>

            <nav>
                <g-link to="/">Home</g-link>
                <g-link href="#">About</g-link>
                <g-link href="#">Contact</g-link>
            </nav>
        </header>
        <ClientOnly>
            <ThemeToggle />
        </ClientOnly>
    </div>
</template>

<script>
export default {
    props: ["siteName"],
    components: {
        ThemeToggle: () => import("@/components/ThemeToggle")
    }
};
</script>
