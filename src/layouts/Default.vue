<template>
    <body class="layout dark">
        <header>
            <strong>
                <g-link to="/">{{ $static.metadata.siteName }}</g-link>
            </strong>
            <nav>
                <g-link to="/">Home</g-link>
                <g-link to="/about/">About</g-link>
                <g-link to="/posts/">Blog</g-link>
            </nav>
        </header>
        <slot />
        <latest-posts />
    </body>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import LatestPosts from "../components/LatestPosts.vue";
export default {
    components: {
        LatestPosts
    }
};
</script>
