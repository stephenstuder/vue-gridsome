<template>
    <body :class="{ light: mode === 'light', dark: mode === 'dark', 'dark oled': mode === 'oled' }">
        <Header :siteName="$page.metadata.siteName" />
        <ClientOnly>
            <ThemeToggle @theme="theme" />
        </ClientOnly>
        <main class="layout">
            <slot />
        </main>
        <footer>
            <h3 class="fake-logo">OliverCSS</h3>
            <nav>
                <a href="/">Home</a>
                <a href="#">About</a>
                <a href="#">Contact</a>
            </nav>
            <p>© 2021 Stephen Studer</p>
        </footer>
    </body>
</template>

<script>
import Header from "@/components/Header";
import ThemeToggle from "@/components/ThemeToggle";

export default {
    components: {
        Header,
        ThemeToggle
    },
    data() {
        return {
            mode: ""
        };
    },
    methods: {
        theme(theme) {
            this.mode = theme;
        }
    },
    updated() {
        this.mode = window.localStorage.theme;
    }
};
</script>
