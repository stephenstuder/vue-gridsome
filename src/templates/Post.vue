<template>
    <Layout>
        <div class="article">
            <h1 class="article-title">{{ $page.post.title }}</h1>
            <p class="article-date">
                {{ $page.post.date }} ·
                <i>{{ $page.post.timeToRead }} min read</i>
            </p>
            <article v-html="$page.post.content" />
        </div>
    </Layout>
</template>

<script>
import Header from "@/components/Header";
export default {
    components: {
        Header
    }
};
</script>

<page-query>
query Post ($path: String!) {
  metadata {
    siteName
    siteDescription
  }
   post: post (path: $path) {
    id
    title
    content
    date (format: "D MMMM YYYY")
    timeToRead
  }
}
</page-query>
